# Swap Elements Between Two Arrays (두 배열의 원소 교체)

> EN Summary: Maximize sum of A by swapping up to K pairs between arrays A and B. Greedy: swap smallest in A with largest in B when beneficial.

---

## Problem

- Two arrays `A`, `B` with `N` natural numbers.
- You can perform at most `K` swaps.
- One swap: choose `A[i]` and `B[j]` and exchange them.
- Goal: **maximize the sum of all elements in A** after swaps.

---

## Input / Output

### Input
- First line: `N K`
- Second line: `A` (N integers)
- Third line: `B` (N integers)

### Output
- Maximum possible `sum(A)` after up to `K` swaps.

---

## Key Idea (Greedy)

✅ Swap **smallest values in A** with **largest values in B**.

Steps:

1. Sort `A` ascending
2. Sort `B` descending
3. For `i = 0..K-1`:
   - if `A[i] < B[i]` → swap
   - else → break (no more benefit)

Why break works:
- `A` gets larger as `i` increases
- `B` gets smaller as `i` increases  
So once `A[i] >= B[i]`, later swaps cannot increase `sum(A)`.

---

## Common Mistakes (내 코드에서 틀릴 수 있는 포인트)

### 1) Input을 grid처럼 받는 실수

```python
list(map(int, input().strip()))
```

- `"123"` 같은 붙은 문자열에서만 의미가 있음
- 이 문제는 `"1 2 3"`처럼 공백 구분 입력이므로

✅ 반드시

```python
list(map(int, input().split()))
```

---

### 2) 이 문제는 “정렬 자체”가 목적이 아님

- 정렬은 도구
- 핵심은 **교환 최적화(그리디)**

---

## Reference Solution (Python)

```python
n, k = map(int, input().split())

A = list(map(int, input().split()))
B = list(map(int, input().split()))

A.sort()              # smallest first
B.sort(reverse=True)  # largest first

for i in range(k):
    if A[i] < B[i]:
        A[i], B[i] = B[i], A[i]
    else:
        break

print(sum(A))
```

---

## Walkthrough Example

Given:

- `A = [1, 2, 5, 4, 3]`
- `B = [5, 5, 6, 6, 5]`
- `K = 3`

Sort:

- `A = [1, 2, 3, 4, 5]`
- `B = [6, 6, 5, 5, 5]`

Swap first K pairs (beneficial only):

- swap `1 ↔ 6`
- swap `2 ↔ 6`
- swap `3 ↔ 5`

Result:

- `A = [6, 6, 5, 4, 5]`
- `sum(A) = 26`

---

## Complexity

- Sorting: `O(N log N)`
- Swaps: `O(K)`  
Total: `O(N log N)`

---

## Notes

- 실전 코테에서는 직접 정렬 구현보다 `sort()` 사용이 정석
- Greedy 판단 포인트: “지금 교환이 무조건 이득인가?” → `A[i] < B[i]`
