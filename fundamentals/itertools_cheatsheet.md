# itertools Cheatsheet (Permutations & Combinations)

> EN Summary: Quick reference for itertools functions frequently used in brute-force and combinatorial problems during coding interviews.

---

## Key Idea

- `permutations` → 순서 O, 중복 X
- `combinations` → 순서 X, 중복 X
- `product` → 순서 O, 중복 O
- `combinations_with_replacement` → 순서 X, 중복 O
- 완전탐색(Brute Force) 문제에서 매우 자주 사용

---

## 1️⃣ Permutations

```python
from itertools import permutations

data = ['A', 'B', 'C']
result = list(permutations(data, 3))
print(result)
```

---

## 2️⃣ Combinations

```python
from itertools import combinations

data = ['A', 'B', 'C']
result = list(combinations(data, 2))
print(result)
```

---

## 3️⃣ Product (Duplicate Permutations)

```python
from itertools import product

data = ['A', 'B', 'C']
result = list(product(data, repeat=2))
print(result)
```

---

## 4️⃣ Combinations with Replacement

```python
from itertools import combinations_with_replacement

data = ['A', 'B', 'C']
result = list(combinations_with_replacement(data, 2))
print(result)
```

---

## When to Use

- 모든 경우의 수를 고려해야 할 때
- Brute Force / 완전탐색 문제
- 조합/순열 직접 구현이 번거로울 때

---

## Complexity

- permutations → O(n!)
- combinations → O(nCr)
- product → O(n^r)

⚠ 경우의 수가 급격히 증가하므로 입력 크기 주의
