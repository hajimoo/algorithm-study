# Greedy: Make N to 1

> EN Summary: Reduce N to 1 using minimal operations. Greedy strategy: divide when possible, otherwise subtract.

---

## 문제

1. N = N - 1  
2. N = N / K (N이 K로 나누어 떨어질 때만)

목표: N을 1로 만드는 최소 연산 횟수

---

## 기본 그리디 풀이

```python
N, K = map(int, input().split())

count = 0

while N > 1:
    if N % K == 0:
        N //= K
    else:
        N -= 1
    count += 1

print(count)
```

---

## 최적화 버전 (점프 방식)

```python
N, K = map(int, input().split())

count = 0

while True:
    target = (N // K) * K
    count += (N - target)
    N = target

    if N < K:
        break

    count += 1
    N //= K

count += (N - 1)
print(count)
```

---

## 시간복잡도

- 기본: O(N)
- 최적화: 나누기 중심 → 더 빠름

---

## 핵심 사고

- 나눌 수 있으면 무조건 나누는 것이 이득
- 나누기 전까지는 -1로 맞춰준다
- 그리디는 "정당성 분석"이 중요

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

