# Adventurer Guild (모험가 길드)

## Problem
공포도 X인 모험가는 X명 이상 그룹에 들어가야 출발 가능  
최대 그룹 수 구하기

## Constraints
N ≤ 100,000

## Strategy (Greedy)
1) 공포도 오름차순 정렬  
2) 한 명씩 그룹에 넣으며 count 증가  
3) count >= 공포도면 그룹 결성 (result += 1, count = 0)

## Code
```python
n = int(input())
data = list(map(int, input().split()))
data.sort()

result = 0
count = 0

for x in data:
    count += 1
    if count >= x:
        result += 1
        count = 0

print(result)
Why This Works
작은 공포도부터 처리하면 “적은 인원으로 그룹을 빠르게 결성” 가능
→ 그룹 수 최대화

Time Complexity
정렬 O(N log N) + 순회 O(N)

