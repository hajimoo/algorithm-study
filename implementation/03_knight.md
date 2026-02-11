# Royal Knight (왕실의 나이트)

## Key Idea
가능한 이동 8가지를 전부 시도 → 경계 안이면 카운트

## Code
```python
pos = input().strip()
row = int(pos[1])
col = ord(pos[0]) - ord('a') + 1

steps = [(-2, -1), (-1, -2), (1, -2), (2, -1),
         (2, 1), (1, 2), (-1, 2), (-2, 1)]

result = 0
for dr, dc in steps:
    nr = row + dr
    nc = col + dc
    if 1 <= nr <= 8 and 1 <= nc <= 8:
        result += 1

print(result)
Reflection
plan/move_types 같은 매핑이 필요 없고
“가능한 경우의 수(8개)” 자체가 고정이므로 전부 시도하면 됨


---

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

