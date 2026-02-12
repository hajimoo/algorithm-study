# Recursion (재귀 함수)

> EN Summary: Understanding recursive functions in Python, including termination conditions, factorial implementation, Euclidean algorithm (GCD), and relationship with DFS.

---

## 1. Recursion 정의

재귀 함수란 자기 자신을 다시 호출하는 함수이다.

⚠ 반드시 종료 조건(Base Case)이 필요하다.

---

## 2. 종료 조건이 없는 경우

```python
def recursive_function():
    print("재귀 호출")
    recursive_function()

recursive_function()
```

- 무한 호출 발생
- RecursionError 발생

---

## 3. 종료 조건 포함 예제

```python
def recursive_function(i):
    if i == 100:
        return

    print(i, "번째 호출")
    recursive_function(i + 1)
    print(i, "번째 종료")

recursive_function(1)
```

- 반드시 `return` 조건 필요
- 호출 이후 코드도 실행됨 (스택 구조 이해 중요)

---

## 4. Factorial

### 수학 정의

```
N! = 1 × 2 × 3 × ... × N
0! = 1
1! = 1
```

---

### 반복 구현

```python
def factorial_iterative(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result
```

---

### 재귀 구현

```python
def factorial_recursive(n):
    if n <= 1:
        return 1
    return n * factorial_recursive(n - 1)
```

---

## 5. GCD – Euclidean Algorithm

### 원리

```
GCD(A, B) = GCD(B, A % B)
```

---

### 예시: GCD(192, 162)

| 단계 | A | B |
|------|----|----|
| 1 | 192 | 162 |
| 2 | 162 | 30 |
| 3 | 30 | 12 |
| 4 | 12 | 6 |

→ 결과: 6

---

### 구현

```python
def gcd(a, b):
    if a % b == 0:
        return b
    return gcd(b, a % b)

print(gcd(192, 162))
```

---

## 6. Recursion 주의사항

- 스택 프레임 사용
- 깊어지면 메모리 사용 증가
- 모든 재귀는 반복문으로 변환 가능
- DFS 구현에 매우 자주 사용됨

---

## Time Complexity

| 알고리즘 | 시간복잡도 | 공간복잡도 |
|------------|------------|------------|
| 팩토리얼 (반복) | O(N) | O(1) |
| 팩토리얼 (재귀) | O(N) | O(N) |
| GCD | O(log N) | O(log N) |
