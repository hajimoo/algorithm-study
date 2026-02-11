# Greedy: Change (Coin Problem)

> EN Summary: Classic greedy example. Always pick the largest coin first when coin system guarantees optimality.

---

## 문제

동전: 500, 100, 50, 10  
거슬러 줄 금액 N이 주어질 때 최소 동전 개수 구하기.

---

## 아이디어

- 가장 큰 화폐 단위부터 선택
- 큰 단위가 항상 작은 단위의 배수일 때 그리디 성립

---

## 코드

```python
n = 1260
count = 0

coin_types = [500, 100, 50, 10]

for coin in coin_types:
    count += n // coin
    n %= coin

print(count)
```

---

## 시간복잡도

- O(K)
- K: 화폐 종류 수

---

## 정당성

- 큰 단위가 작은 단위의 배수
- 큰 단위를 먼저 쓰는 것이 항상 최소 개수 보장

---

## 반례 예시

화폐 단위가 500, 400, 100이라면  
그리디가 항상 최적을 보장하지 않음.
