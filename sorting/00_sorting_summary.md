# Sorting Algorithms Summary

> Quick comparison of major sorting algorithms for coding interviews.

---

## Sorting Comparison Table

| Algorithm | Avg Time | Space | 특징 |
|----------|---------|------|------|
| Selection Sort | O(N²) | O(1) | 구현 매우 쉬움 |
| Insertion Sort | O(N²) | O(1) | 거의 정렬된 경우 매우 빠름 |
| Quick Sort | O(N log N) | O(log N) recursion | 대부분 상황에서 빠름 |
| Counting Sort | O(N + K) | O(N + K) | 값 범위 제한 시 매우 빠름 |

---

## Python Built-in Sort

Python의 `sorted()` 와 `list.sort()` 는

👉 **Timsort**

특징:

- 평균 O(N log N)
- 최악 O(N log N)
- stable sort
- 실제 환경에서 매우 빠름

---

## ⭐ 코딩테스트 판단 기준 (VERY IMPORTANT)

### 1️⃣ 그냥 정렬 문제

```python
sorted(array)
```

👉 대부분 이걸로 끝

---

### 2️⃣ 값 범위 작음 + 정수

👉 Countin
