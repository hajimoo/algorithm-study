# Sorting Speed Comparison (Selection vs Python sort)

> Simple experiment comparing naive selection sort with Python built-in sort.

---

## Why this matters

코딩 테스트에서 직접 정렬 구현보다

👉 Python의 `sort()` / `sorted()` 사용이 훨씬 빠름.

이 실험은 그 차이를 확인하기 위한 코드.

---

## Full Python Code

```python
from random import randint
import time

# ------------------------
# 랜덤 배열 생성 (10,000개)
# ------------------------
array = []
for _ in range(10000):
    array.append(randint(1, 100))

# ------------------------
# Selection Sort 성능 측정
# ------------------------
start_time = time.time()

for i in range(len(array)):
    min_index = i
    for j in range(i + 1, len(array)):
        if array[min_index] > array[j]:
            min_index = j
    array[i], array[min_index] = array[min_index], array[i]

end_time = time.time()

print("Selection sort time:", end_time - start_time)


# ------------------------
# 배열 다시 생성
# ------------------------
array = []
for _ in range(10000):
    array.append(randint(1, 100))

# ------------------------
# Python sort 성능 측정
# ------------------------
start_time = time.time()

array.sort()

end_time = time.time()

print("Python sort time:", end_time - start_time)
```

---

## Example Result (환경마다 다름)

```
Selection sort time: 35.84
P
