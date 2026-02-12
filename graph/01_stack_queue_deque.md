# Stack / Queue / deque

> EN Summary: Basic stack and queue implementation in Python. Use list for stack and collections.deque for queue for O(1) operations.

---

## Stack (LIFO)

- Last In First Out
- 파이썬에서는 list로 구현 가능
- append() / pop() 모두 O(1)

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

# 출력
print(stack[::-1])  # 최상단부터 출력
print(stack)        # 최하단부터 출력
```

### 시간복잡도
- append(): O(1)
- pop(): O(1)

---

## Queue (FIFO)

- First In First Out
- list 대신 deque 사용 (성능 차이 중요)

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

### 왜 deque를 쓰는가?

- list.pop(0)은 O(N)
- deque.popleft()는 O(1)
- BFS 구현 시 필수

---

## reverse()

```python
queue.reverse()
print(queue)
```

---

## 핵심 정리

- 스택 → list 사용
- 큐 → deque 사용
- BFS는 deque가 사실상 필수
