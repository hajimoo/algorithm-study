# Lambda & map (Python)

> EN Summary: Usage of lambda expressions and the map function in Python, commonly applied in sorting and functional-style transformations during coding tests.

---

## Key Idea

- `lambda`는 간단한 함수를 한 줄로 정의할 때 사용
- 정렬의 `key` 인자로 자주 사용됨
- `map()`은 iterable의 각 원소에 함수를 적용할 때 사용

---

## 1️⃣ 함수로 key 지정

```python
array = [('홍길동', 50), ('이순신', 32), ('아무도', 74)]

def my_key(x):
    return x[1]

print(sorted(array, key=my_key))
```

---

## 2️⃣ lambda로 축약

```python
array = [('홍길동', 50), ('이순신', 32), ('아무도', 74)]

print(sorted(array, key=lambda x: x[1]))
```

---

## 언제 lambda를 쓰는가?

- 재사용 필요 없음 → `lambda`
- 재사용 필요 / 가독성 중요 → 일반 함수

---

## 3️⃣ map 사용 예시

```python
list1 = [1, 2, 3, 4, 5]
list2 = [6, 7, 8, 9, 10]

result = map(lambda a, b: a + b, list1, list2)
print(list(result))
```

---

## 언제 map을 쓰는가?

- 각 원소에 동일한 연산을 적용할 때
- 반복문을 간결하게 표현하고 싶을 때

---

## Complexity

- `sorted()` → O(N log N)
- `map()` → O(N)
