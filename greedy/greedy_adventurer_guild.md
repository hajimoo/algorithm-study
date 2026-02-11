# Greedy: Adventurer Guild

> EN Summary: Sort fear levels ascending. Form a group when current count >= fear level.

---

## 문제

공포도 X인 모험가는 X명 이상인 그룹에 포함되어야 함.  
최대 그룹 수 구하기.

---

## 아이디어

1. 공포도 오름차순 정렬
2. count 증가
3. count >= 현재 공포도 → 그룹 결성

---

## 코드

```python
n = int(input())
data = list(map(int, input().split()))
data.sort()

count = 0
result = 0

for x in data:
    count += 1
    if count >= x:
        result += 1
        count = 0

print(result)
```

---

## 시간복잡도

- O(N log N)

---

## 핵심 사고

- 작은 공포도부터 처리해야 그룹 수가 최대가 됨.
