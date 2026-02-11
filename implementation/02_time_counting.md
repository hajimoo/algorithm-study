# Time Counting (시각)

## Idea
모든 시간을 완전탐색으로 돌면서 '3' 포함 여부 체크

## Constraints
N ≤ 23 → 24*60*60 = 86,400 (상수급)

## Code
```python
h = int(input())
count = 0

for i in range(h + 1):
    for j in range(60):
        for k in range(60):
            if '3' in str(i) + str(j) + str(k):
                count += 1

print(count)
Time Complexity
O(24 * 60 * 60) = O(1) 느낌으로 충분히 가능
