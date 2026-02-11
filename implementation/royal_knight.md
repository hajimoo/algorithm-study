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

## `implementation/04_string_rearrangement.md` (문자열 재정렬)

```markdown
# String Rearrangement (문자열 재정렬)

## Strategy
- 알파벳은 따로 모아서 정렬
- 숫자는 합산
- 알파벳 + 숫자합 출력

## Code
```python
s = input().strip()

letters = []
value = 0

for ch in s:
    if ch.isalpha():
        letters.append(ch)
    else:
        value += int(ch)

letters.sort()

if value != 0:
    result = ''.join(letters) + str(value)
else:
    result = ''.join(letters)

print(result)
Time Complexity
정렬 포함 O(N log N)

