# Stack / Queue / deque

> EN Summary: Basic stack and queue implementation in Python. Use `list` for stack and `collections.deque` for queue to achieve O(1) operations.

---

## 1. Stack (LIFO)

**Last In First Out**

- Python에서는 `list`로 구현
- `append()` / `pop()` → O(1)

```python
stack = []

# 삽입
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)

# 삭제
stack.pop()

stack.append(1)
stack.append(4)
stack.pop()

print(stack[::-1])  # top부터 출력
print(stack)        # bottom부터 출력
```

### Time Complexity

| Operation | Complexity |
|------------|------------|
| append()   | O(1) |
| pop()      | O(1) |

---

## 2. Queue (FIFO)

**First In First Out**

- `list` 대신 `deque` 사용 (성능 차이 중요)

```python
from collections import deque

queue = deque()

queue.append(5)
queue.append(2)
queue.append(3)
queue.append(7)
queue.popleft()

queue.append(1)
queue.append(4)
queue.popleft()

print(list(queue))
```

---

## Why deque?

| Structure | pop(0) | popleft() |
|------------|--------|------------|
| list       | O(N)   | ❌ |
| deque      | -      | O(1) |

- `list.pop(0)` → 전체 요소 이동 발생 (O(N))
- `deque.popleft()` → O(1)
- BFS 구현 시 필수

---

## reverse()

```python
queue.reverse()
print(queue)
```

---

## 핵심 정리

- Stack → `list`
- Queue → `deque`
- BFS → `deque` 필수

