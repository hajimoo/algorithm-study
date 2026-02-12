# DFS (Depth-First Search)

> EN Summary: DFS explores as deep as possible before backtracking. Implemented using recursion or stack.

---

## 1. DFS 동작 과정

1. 시작 노드를 방문 처리
2. 방문하지 않은 인접 노드를 재귀적으로 방문
3. 더 이상 방문할 노드가 없으면 되돌아감

---

## 2. 예시 그래프 (인접 리스트)

```python
graph = [
    [],
    [2, 3, 8],
    [1, 7],
    [1, 4, 5],
    [3, 5],
    [3, 4],
    [7],
    [2, 6, 8],
    [1, 7]
]
```

---

## 3. DFS 구현 (재귀)

```python
def dfs(graph, v, visited):
    visited[v] = True
    print(v, end=" ")

    for i in graph[v]:
        if not visited[i]:
            dfs(graph, i, visited)

visited = [False] * 9
dfs(graph, 1, visited)
```

---

## 4. 탐색 순서 예시

1 → 2 → 7 → 6 → 8 → 3 → 4 → 5

---

## Time Complexity

- 인접 리스트 기준: O(V + E)
