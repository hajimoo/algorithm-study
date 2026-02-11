# Change (거스름돈)

## Problem
500, 100, 50, 10 동전이 무한히 있을 때
N원을 거슬러줄 최소 동전 개수 (N은 10의 배수)

## Strategy
큰 단위부터 최대한 사용

## Code
```python
n = 1260
count = 0
coin_types = [500, 100, 50, 10]

for coin in coin_types:
    count += n // coin
    n %= coin

print(count)
Correctness (정당성)
큰 단위가 항상 작은 단위의 배수라서
큰 단위부터 greedy로 선택해도 최적해가 보장됨

Time Complexity
동전 종류 K개 → O(K)

Counter Example (왜 정당성 체크가 필요한가)
동전이 500, 400, 100이면
큰 단위부터가 항상 최적이 아닐 수 있음
