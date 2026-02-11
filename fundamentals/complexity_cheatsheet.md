# Time Complexity Cheatsheet

> EN Summary: Quick reference for deciding algorithm feasibility under 1 second time limit.

---

## 기본 복잡도

- O(1)      : 상수
- O(log N)  : 이진 탐색
- O(N)      : 1회 순회
- O(N log N): 정렬
- O(N²)     : 이중 반복
- O(2ⁿ)     : 완전 탐색

---

## 1초 제한 감각표

- N ≤ 500       → O(N³) 가능
- N ≤ 2,000     → O(N²) 가능
- N ≤ 100,000   → O(N log N) 가능
- N ≤ 10,000,000 → O(N) 가능

---

## 문제 접근 루틴

1. 입력 크기 확인
2. 시간복잡도 계산
3. 가능 여부 판단
4. 알고리즘 선택

---

## 중요

- 위 표는 감각용
- 애매하면 직접 계산
- N 범위는 알고리즘 힌트
