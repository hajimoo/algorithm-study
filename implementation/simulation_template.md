# Simulation Problem Template

> EN Summary: General template for grid/simulation problems. Define state → map commands → validate → update.

---

## 구현 문제 풀이 루틴

### 1️⃣ 입력 받기
- 격자 크기
- 명령 리스트
- 기타 조건

---

### 2️⃣ 상태(State) 정의
- 현재 위치 (x, y)
- 방향
- 시간
- 체력
- 보드 상태

---

### 3️⃣ 명령 → 변화량 매핑

### 방법 1: 리스트 매핑

```python
dx = [0, 0, -1, 1]
dy = [-1, 1, 0, 0]
move_types = ['L', 'R', 'U', 'D']
```

---

### 방법 2: 딕셔너리 매핑 (추천)

```python
move = {
    'L': (0, -1),
    'R': (0, 1),
    'U': (-1, 0),
    'D': (1, 0)
}
```

---

### 4️⃣ 반복 구조

```python
for m in data:
    dx, dy = move[m]
    nx = x + dx
    ny = y + dy

    if 1 <= nx <= n and 1 <= ny <= n:
        x, y = nx, ny
```

---

## 체크 포인트

- 반복 기준은 격자(n)가 아니라 명령(data)
- 경계 조건 반드시 확인
- 상태 업데이트 위치 확인

---

## 핵심 구조

상태 정의 → 명령 반복 → 제약 검사 → 상태 갱신
