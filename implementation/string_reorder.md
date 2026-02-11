# Implementation: String Reorder

> EN Summary: Given an alphanumeric string, sort all letters and append the sum of all digits at the end (common string parsing + sorting pattern).

---

## Key Idea

- 문자를 하나씩 보면서
  - 알파벳이면 리스트에 모음
  - 숫자면 합(sum)에 누적
- 알파벳 리스트를 정렬한 뒤
- `알파벳들 + 숫자합` 형태로 출력

---

## Implementation

```python
s = input().strip()

letters = []
digit_sum = 0

for ch in s:
    if ch.isalpha():
        letters.append(ch)
    else:
        digit_sum += int(ch)

letters.sort()

# 숫자 합이 0이 아닌 경우에만 뒤에 붙이기 (문제 조건에 따라 선택)
if digit_sum != 0:
    result = ''.join(letters) + str(digit_sum)
else:
    result = ''.join(letters)

print(result)
```

---

## Complexity

- Time: O(N log N)  (정렬 때문에)
- Space: O(N)

---

## Notes

- `isalpha()` / `isdigit()`로 문자를 분기하면 구현이 단순해짐
- 숫자 합이 0일 때도 `0`을 붙여야 하는지 여부는 문제 요구사항에 따라 결정
  - 일반적으로 “숫자를 더한 값”을 붙이는 형태라면 0이면 생략하는 풀이가 많음
- 입력이 매우 길어도(예: 10,000) 정렬은 충분히 가능
