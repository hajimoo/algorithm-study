# itertools Cheatsheet (Perm / Comb)

## 1️⃣ 순열 (permutations)

```python
from itertools import permutations

data = ['A', 'B', 'C']
result = list(permutations(data, 3))
print(result)
```

---

## 2️⃣ 조합 (combinations)

```python
from itertools import combinations

data = ['A', 'B', 'C']
result = list(combinations(data, 2))
print(result)
```

---

## 3️⃣ 중복 순열 (product)

```python
from itertools import product

data = ['A', 'B', 'C']
result = list(product(data, repeat=2))
print(result)
```

---

## 4️⃣ 중복 조합 (combinations_with_replacement)

```python
from itertools import combinations_with_replacement

data = ['A', 'B', 'C']
result = list(combinations_with_replacement(data, 2))
print(result)
```

---

## 언제 쓰나?

👉 모든 경우의 수를 고려해야 할 때 (완전탐색)
