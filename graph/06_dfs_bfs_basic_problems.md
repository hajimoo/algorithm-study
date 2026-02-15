# DFS / BFS Basic Problems

> EN Summary: Classic grid traversal problems solved using DFS and BFS. Includes counting connected components and shortest path in maze.

---

# 1. Ice Cream Freeze (음료수 얼려 먹기)

## Problem

- N × M 얼음 틀
- 0 = 구멍 (연결 가능)
- 1 = 칸막이
- 상/하/좌/우 연결된 0은 하나의 아이스크림

👉 생성되는 아이스크림 개수 구하기

---

## Example

```
4 5
00110
00011
11111
00000
```

Output

```
3
```

---

## Approach

이 문제는 **연결 요소 개수 세기 문제**

- 그래프 모델링 가능
- DFS 또는 BFS 사용 가능
- 방문하지 않은 0을 발견하면 DFS 수행 후 count++

---

## DFS Logic

1. 현재 위치가 범위를 벗어나면 종료
2. 값이 0이면 방문 처리 후
3. 상/하/좌/우 재귀 호출
4. 처음 방문한 경우 True 반환 → count++

---

## Python Solution (DFS)

```python
def dfs(x, y):
    if x < 0 or x >= n or y < 0 or y >= m:
        return False

    if graph[x][y] == 0:
        graph[x][y] = 1

        dfs(x-1, y)
        dfs(x+1, y)
        dfs(x, y-1)
        dfs(x, y+1)

        return True

    return False


n, m = map(int, input().split())

graph = []
for _ in range(n):
    graph.append(list(map(int, input().strip())))

result = 0

for i in range(n):
    for j in range(m):
        if dfs(i, j):
            result += 1

print(result)
```

---

## 핵심 포인트

- 연결 요소 개수 세기
- DFS 기본 연습용 문제
- flood fill 유형

---

---

# 2. Maze Escape (미로 탈출)

## Problem

- 시작: (1,1)
- 목표: (N,M)
- 0 = 이동 불가
- 1 = 이동 가능
- 상/하/좌/우 이동 가능

👉 최소 이동 칸 수 구하기

---

## Example

```
5 6
101010
111111
000001
111111
111111
```

Output

```
10
```

---

## Approach

이 문제는 **최단 거리 문제**

- BFS 사용
- 이동할 때마다 거리 +1
- graph에 거리 직접 기록 가능

---

## Python Solution (BFS)

```python
from collections import deque

n, m = map(int, input().split())

graph = [list(map(int, input().strip())) for _ in range(n)]

dx = [-1,1,0,0]
dy = [0,0,-1,1]

def bfs(x, y):
    queue = deque([(x, y)])

    while queue:
        x, y = queue.popleft()

        for i in range(4):
            nx = x + dx[i]
            ny = y + dy[i]

            if nx < 0 or nx >= n or ny < 0 or ny >= m:
                continue

            if graph[nx][ny] == 0:
                continue

            if graph[nx][ny] == 1:
                graph[nx][ny] = graph[x][y] + 1
                queue.append((nx, ny))

    return graph[n-1][m-1]

print(bfs(0,0))
```

---

## 핵심 포인트

- BFS → 최단거리
- queue 사용 필수
- 방문 체크 대신 거리 갱신

---

---

# Pattern Recognition (코테 핵심)

### DFS 사용하는 경우

- 연결 요소 개수
- 영역 개수
- flood fill

→ Ice Cream 문제

---

### BFS 사용하는 경우

- 최단거리
- 최소 이동 횟수
- 단계별 탐색

→ Maze 문제

---

---
