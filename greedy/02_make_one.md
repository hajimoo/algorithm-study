# Make One (1이 될 때까지)

## Operations
1) N = N - 1  
2) N = N / K (N이 K로 나누어떨어질 때만)

## Goal
N을 1로 만드는 최소 연산 횟수

## Greedy Idea
- 나눌 수 있으면 나누는 게 큰 폭 감소라 이득
- 나누기 전까지는 -1로 나눠떨어지게 만든다

## Simple Code
```python
n, k = map(int, input().split())
count = 0

while n > 1:
    if n % k == 0:
        n //= k
    else:
        n -= 1
    count += 1

print(count)
Optimized Code (점프)
n, k = map(int, input().split())
count = 0

while True:
    target = (n // k) * k
    count += (n - target)
    n = target

    if n < k:
        break

    count += 1
    n //= k

count += (n - 1)
print(count)
Time Complexity
단순: 최악 O(N)

점프: 나누기 중심으로 더 빠름

