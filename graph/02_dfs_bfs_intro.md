# DFS / BFS Intro

> EN Summary: Core graph traversal algorithms. DFS explores deeply using stack/recursion. BFS explores level-by-level using queue and is used for shortest path in unweighted graphs.

---

## Search (탐색)

많은 데이터 중 원하는 데이터를 찾는 과정.

그래프 탐색 대표 알고리즘:

- DFS (Depth-First Search)
- BFS (Breadth-First Search)

---

## 1. DFS (Depth-First Search)

깊이 우선 탐색

- 스택 기반
- 또는 재귀 기반
- 한 방향으로 깊게 탐색

### 사용 상황

- 경로 탐색
- 백트래킹
- 사이클 탐지

---

## 2. BFS (Breadth-First Search)

너비 우선 탐색

- 큐 기반
- 가까운 노드부터 확장

### 사용 상황

- 최단거리 (간선 가중치 동일)
- 레벨 탐색

---

## DFS vs BFS 비교

| 구분 | DFS | BFS |
|------|------|------|
| 자료구조 | Stack / Recursion | Queue |
| 탐색 방식 | 깊게 | 넓게 |
| 최단거리 | ❌ | ✅ (가중치 동일) |
| 메모리 사용 | 비교적 적음 | 비교적 많음 |

---

## 코테 중요도

- DFS / BFS는 코딩테스트 필수
- 그래프 문제의 기본 뼈대


- 경로 탐색
- 백트래킹
- 사이클 탐지

---

## 2. BFS (Breadth-First Search)

너비 우선 탐색

- 큐 기반
- 가까운 노드부터 확장

### 사용 상황

