# Greedy: Multiply or Add

> EN Summary: When processing digits left-to-right, add if either number is 0 or 1, otherwise multiply.

---

## 문제

숫자로 구성된 문자열 S가 주어짐.  
왼쪽부터 계산하여 가장 큰 수 만들기.

---

## 핵심 아이디어

- 0 또는 1이면 더하기
- 그 외에는 곱하기

---

## 코드

```python
data = input()

result = int(data[0])

for i in range(1, len(data)):
    num = int(data[i])
    if num <= 1 or result <= 1:
        result += num
    else:
        result *= num

print(result)
```

---

## 시간복잡도

- O(N)

---

## 실수 포인트

- 1은 곱하는 것이 이득이 아님
- 입력은 문자열로 받는 것이 효율적
