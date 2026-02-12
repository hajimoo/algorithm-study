# BFS (Breadth-First Search)

> EN Summary: BFS explores nodes level-by-level using queue. Used for shortest path in unweighted graphs.

---

## 1. BFS 동작 과정

1. 시작 노드를 큐에 삽입하고 방문 처리
2. 큐에서 노드를 꺼내 인접 노드 방문
3. 방문하지 않은 노드를 큐에 삽입
4. 큐가 빌 때까지 반복

---

## 2. 구현

```python
from collections import deque

def bfs(graph, start, visited):
    queue = deque([start])
    visited[start] = True

    while queue:
        v = queue.popleft()
        print(v, end=" ")

        for i in graph[v]:
            if not visited[i]:
                queue.append(i)
                visited[i] = True

visited = [False] * 9
bfs(graph, 1, visited)
```

---

## 3. 탐색 순서 예시

1 → 2 → 3 → 8 → 7 → 4 → 5 → 6

---

## 4. 특징

- 최단거리 탐색 가능 (간선 가중치 동일)
- 레벨 탐색에 적합

---

## Time Complexity

- 인접 리스트 기준: O(V + E)
