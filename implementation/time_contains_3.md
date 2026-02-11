# Implementation: Time (Contains 3)

> EN Summary: Brute force over hours, minutes, seconds. Check if '3' in string.

---

## 문제

00:00:00 ~ N:59:59 중  
숫자 3이 포함된 시각 개수 구하기.

---

## 코드

```python
n = int(input())
count = 0

for h in range(n + 1):
    for m in range(60):
        for s in range(60):
            if '3' in str(h) + str(m) + str(s):
                count += 1

print(count)
```

---

## 시간복잡도

- O(N × 60 × 60)
- N ≤ 23 → 충분히 가능

---

## 핵심

- 완전탐색
- 범위가 작으면 브루트포스가 정답
