# collections.Counter

Counter는 “등장 횟수”를 세는 자료구조

```python
from collections import Counter

counter = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])

print(counter['blue'])   # 3
print(counter['green'])  # 1
print(dict(counter))     # {'red':2, 'blue':3, 'green':1}
✅ 팁

문자열/리스트 등 iterable이면 바로 카운트 가능

“최빈값”, “빈도 비교” 문제에서 자주 사용

