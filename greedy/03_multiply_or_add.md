# Multiply or Add (곱하기 혹은 더하기)

## Key Insight
0이나 1이 끼면 곱하기보다 더하기가 유리함  
(1은 곱해도 값이 안 커짐)

## Code
```python
data = input().strip()
result = int(data[0])

for i in range(1, len(data)):
    num = int(data[i])
    if num <= 1 or result <= 1:
        result += num
    else:
        result *= num

print(result)
Time Complexity
O(N)

Reflection
처음에 1을 예외로 처리하지 않으면 최댓값이 깨질 수 있음

