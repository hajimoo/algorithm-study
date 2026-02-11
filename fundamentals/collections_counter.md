# collections.Counter

> EN Summary: Count frequency of elements in iterable.

---

## 예시

```python
from collections import Counter

counter = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])

print(counter['blue'])
print(counter['green'])
print(dict(counter))
```

---

## 시간복잡도

- O(N)

---

## 언제 쓰는가?

- 빈도수 계산
- 가장 많이 등장한 값 찾기
