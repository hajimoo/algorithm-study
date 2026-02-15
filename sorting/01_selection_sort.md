# Selection Sort (선택 정렬)

> EN Summary: Selection sort repeatedly finds the minimum element from the unsorted part and places it at the beginning. Simple but inefficient for large inputs.

---

## Sorting이란?

데이터를 특정 기준에 따라 순서대로 나열하는 것.

문제 상황에 따라 적절한 정렬 알고리즘을 선택해야 한다.

---

# Selection Sort 개념

처리되지 않은 데이터 중에서

👉 **가장 작은 값을 선택하여 맨 앞의 값과 교환**

이 과정을 반복한다.

---

## Example

초기 배열

```
[7, 5, 9, 0, 3, 1, 6, 2, 4, 8]
```

---

### Step 0

가장 작은 값 0 선택 → 첫 번째 값 7과 교환

```
[0, 5, 9, 7, 3, 1, 6, 2, 4, 8]
```

---

### Step 1

남은 부분에서 최소값 1 선택 → 5와 교환

```
[0, 1, 9, 7, 3, 5, 6, 2, 4, 8]
```

---

### Step 2

최소값 2 선택 → 9와 교환

```
[0, 1, 2, 7, 3, 5, 6, 9, 4, 8]
```

---

### Step 3

최소값 3 선택 → 7과 교환

```
[0, 1, 2, 3, 7, 5, 6, 9, 4, 8]
```

---

… 반복 …

---

### 최종 결과

```
[0,1,2,3,4,5,6,7,8,9]
```

---

# Python Implementation

```python
array = [7,5,9,0,3,1,6,2,4,8]

for i in range(len(array)):
    min_index = i #가장 작은 원소의 인덱스

    for j in range(i+1, len(array)):
        if array[min_index] > array[j]:
            min_index = j

    array[i], array[min_index] = array[min_index], array[i] #스와프

print(array)
```

---

# Time Complexity

| Case | Complexity |
|------|------------|
| Best | O(N²) |
| Avg  | O(N²) |
| Worst| O(N²) |

- 항상 전체 탐색 필요
- 입력 상태와 관계없이 동일

---

# 특징

- 구현 매우 쉬움
- 교환 횟수 적음
- 하지만 매우 느림
- 실제 코테에서는 거의 사용 안함

👉 **정렬 알고리즘 개념 이해용**

---

# 언제 등장하나 (코테 기준)

- 정렬 원리 설명 문제
- 작은 입력 크기
- 알고리즘 교육용 문제

실전에서는 보통

- Python `sorted()`
- 또는 `sort()`

사용한다.
