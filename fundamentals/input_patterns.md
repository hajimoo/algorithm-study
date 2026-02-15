# Input Patterns (Python)

> EN Summary: Common input handling patterns in Python for coding interviews, including fast I/O using sys.stdin.readline.

---

## Key Idea

- 기본 입력은 `input()` 사용
- 공백 구분 데이터는 `split()` + `map()` 패턴
- 입력이 많은 경우 `sys.stdin.readline()` 사용

---

## 1️⃣ Single Integer

```python
n = int(input())
```

---

## 2️⃣ Space-Separated Integers

```python
data = list(map(int, input().split()))
```

---

## 3️⃣ Split After Storing Input

```python
input_data = input()
data = list(map(int, input_data.split()))
```

---

## 4️⃣ Fast Input (Large Data)

```python
import sys
input = sys.stdin.readline

line = input().rstrip()
```

## 5️⃣ Read digits directly into a list

```python

graph.append(list(map(int, input())))

---

## When to Use Fast Input

- 입력 줄 수가 많을 때 (예: 100,000 이상)
- 시간 제한이 빡빡한 문제
- 반복적으로 입력을 받을 때

---

## Complexity

- `input()` → O(N)
- `sys.stdin.readline()` → 더 빠른 I/O 처리
- 알고리즘 복잡도에는 영향 없음 (입출력 속도 개선 목적)

---

## Notes

- `rstrip()`은 개행 문자(`\n`) 제거용
- `input = sys.stdin.readline`으로 치환하면 타이핑 감소
- 문자열 따옴표는 일반 `'`, `"` 사용
