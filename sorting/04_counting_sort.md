# Counting Sort (계수 정렬)

> EN Summary: Counting sort counts occurrences of each value and reconstructs the sorted output. Extremely fast when value range is small.

---

## 개념

특정 조건에서만 사용 가능하지만

👉 매우 빠른 정렬 알고리즘.

---

## 사용 조건

- 데이터가 **정수**
- 값의 범위가 제한됨
- 최대값이 너무 크지 않음

---

## 핵심 아이디어

1. 데이터 값 범위 크기의 리스트 생성
2. 각 값 등장 횟수 기록
3. count 배열 순서대로 값 출력

---

## Example

정렬 데이터

```
7 5 9 0 3 1 6 2 9 1 4 8 0 5 2
```

---

### Step 1

값 범위 만큼 count 리스트 생성

```
count = [0,0,0,0,0,0,0,0,0,0]
```

---

### Step 2

데이터 하나씩 보면서 count 증가

```
count[7] += 1
count[5] += 1
count[9] += 1
...
```

---

### 최종 count 배열

```
[2,2,2,1,1,2,1,1,1,2]
```

---

### 결과 출력

count[i] 값 만큼 i 출력

```
0 0 1 1 2 2 3 4 5 5 6 7 8 9 9
```

---

# Python Implementation

```python
array = [7,5,9,0,3,1,6,2,9,1,4,8,0,5,2]

count = [0] * (max(array) + 1)

for i in range(len(array)):
    count[array[i]] += 1

for i in range(len(count)):
    for _ in range(count[i]):
        print(i, end=" ")
```

---

# Time Complexity

| Complexity |
|------------|
| O(N + K) |

- N = 데이터 개수
- K = 값 범위 크기

---

# Space Complexity

| Complexity |
|------------|
| O(N + K) |

---

## ⭐ 장점

- 매우 빠름
- 비교 연산 없음
- O(N log N)보다 빠를 수 있음

---

## ⚠️ 단점

값 범위가 크면 메모리 폭발

예:

```
데이터: [1, 1000000000]
```

→ count 배열 10억 크기 필요 → 불가능

---

# 언제 코테에서 쓰나 (⭐⭐⭐⭐ 중요)

이 조건 보이면 거의 무조건 Counting Sort:

- 값 범위 작음
- 정수만 존재
- 중복 많음
- N 매우 큼 (10^6 이상)

---

# 코테에서 매우 자주 나오는 형태

예:

- 학생 점수 정렬 (0~100)
- 숫자 등장 횟수 정렬
- 작은 범위 숫자 대량 입력

---

# Python 현실

대부분 경우

```python
sorted(array)
```

쓰지만

👉 값 범위 작고 데이터 많으면 Counting Sort가 더 빠름.
