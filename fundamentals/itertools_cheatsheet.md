itertools Cheatsheet (Perm/Comb)

1) 순열 permutations
```python
from itertools import permutations
data = ['A', 'B', 'C']
result = list(permutations(data, 3))
print(result)

2) 조합
combinations from itertools import combinations
data = ['A', 'B', 'C']
result = list(combinations(data, 2))
print(result)

3) 중복 순열
product from itertools import product
data = ['A', 'B', 'C']
result = list(product(data, repeat=2))
print(result)

4) 중복 조합
combinations_with_replacement from itertools import combinations_with_replacement
data = ['A', 'B', 'C']
result = list(combinations_with_replacement(data, 2))
print(result)

언제 쓰나?

“모든 경우의 수”를 고려해야 할 때 (완전탐색)


---
