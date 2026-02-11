# Implementation: Royal Knight

> EN Summary: Try all 8 knight moves and count valid positions.

---

## 문제

체스판 8x8에서 나이트 이동 가능한 경우의 수 구하기.

---

## 코드

```python
input_data = input().strip()

row = int(input_data[1])
column = ord(input_data[0]) - ord('a') + 1

steps = [
    (-2, -1), (-1, -2),
    (1, -2), (2, -1),
    (2, 1), (1, 2),
    (-1, 2), (-2, 1)
]

result = 0

for step in steps:
    next_row = row + step[0]
    next_column = column + step[1]

    if 1 <= next_row <= 8 and 1 <= next_column <= 8:
        result += 1

print(result)
```

---

## 시간복잡도

- O(1)

---

## 핵심

- 이동 가능한 8가지 경우 모두 시도
- 범위 체크 필수
