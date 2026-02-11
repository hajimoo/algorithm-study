# Stack & Queue (Python)

## Stack
LIFO (Last In First Out)

```python
stack = []
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

print(stack[::-1])  # top부터
print(stack)        # bottom부터
append/pop: 평균 O(1)

Queue
FIFO (First In First Out)
파이썬 list로 pop(0) 하면 느림 → deque 사용

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

print(list(queue))  # 먼저 들어온 순서
queue.reverse()
print(queue)
✅ deque는 popleft가 O(1)에 가까워서 효율적


---

## `graph/01_dfs_bfs_intro.md`

```markdown
# DFS / BFS Intro

## Search (탐색)
많은 데이터 중 원하는 데이터를 찾는 과정

그래프 탐색에서 대표 알고리즘:
- DFS (Depth-First Search)
- BFS (Breadth-First Search)

## DFS
- 스택(재귀) 기반으로 “깊게” 들어감
- 경로 탐색/백트래킹에서 자주 사용

## BFS
- 큐 기반으로 “가까운 것부터” 확장
- 최단거리(간선 가중치 동일)에서 자주 사용

✅ 코테에서 매우 자주 등장 → 반드시 숙지
