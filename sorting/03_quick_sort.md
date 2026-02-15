# Quick Sort (퀵 정렬)

> EN Summary: Quick sort is a divide-and-conquer sorting algorithm that partitions data using a pivot and recursively sorts the subarrays. Average O(N log N).

---

## 개념

기준 데이터(Pivot)를 설정하고

👉 pivot보다 작은 데이터는 왼쪽  
👉 pivot보다 큰 데이터는 오른쪽  

으로 나눈 뒤

각 부분을 다시 정렬한다.

이 과정을 반복한다.

---

## 핵심 아이디어

1. pivot 선택 (보통 첫 번째 원소)
2. 왼쪽에서 pivot보다 큰 값 찾기
3. 오른쪽에서 pivot보다 작은 값 찾기
4. 두 값 위치 교환
5. 포인터가 엇갈리면 pivot과 작은 값 교환
6. pivot 기준으로 좌우 분할
7. 좌우 배열 재귀 정렬

---

## Example

```
[5,7,9,0,3,1,6,2,4,8]
```

pivot = 5

분할 후:

```
[1,4,2,0,3] 5 [6,9,7,8]
```

왼쪽과 오른쪽 각각 다시 정렬 수행.

---

# Python Implementation (In-place Quick Sort)

```python
array = [5,7,9,0,3,1,6,2,4,8]

def quick_sort(array, start, end):

    if start >= end: #원소가 1개인 경우 종
        return

    pivot = start # 피벗은 첫번째 원
    left = start + 1
    right = end

    while left <= right:
            # 피벗보다 큰 데이터를 찾을 때까지 반복 
        while left <= end and array[left] <= array[pivot]:
            left += 1
           #피벗보다 작은 데이터를 찾을 떄까지 반복
        while right > start and array[right] >= array[pivot]:
            right -= 1

        if left > right: # 엇갈렸다면 작은 데이터와 피벗을 교
            array[right], array[pivot] = array[pivot], array[right]
        else: #엇갈리지 않았다면 작은 데이터와 큰 데이터을 교체
            array[left], array[right] = array[right], array[left]
    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
    quick_sort(array, start, right - 1)
    quick_sort(array, right + 1, end)


quick_sort(array, 0, len(array)-1)
print(array)
```

---

# Python Implementation (Simple Version — Interview Friendly)

```python
def quick_sort(array):

    if len(array) <= 1:
        return array

    pivot = array[0]
    tail = array[1:]

    left = [x for x in tail if x <= pivot]
    right = [x for x in tail if x > pivot]

    return quick_sort(left) + [pivot] + quick_sort(right)


print(quick_sort([5,7,9,0,3,1,6,2,4,8]))
```

---

# Time Complexity

| Case | Complexity |
|------|------------|
| Best | O(N log N) |
| Avg  | O(N log N) |
| Worst| O(N²) |

---

## 왜 최악이 발생하나?

이미 정렬된 배열에서

pivot을 첫 번째 값으로 계속 선택하면

```
[1,2,3,4,5,6,7,8,9]
```

→ 한쪽만 계속 분할됨  
→ O(N²)

---

# 특징

- 매우 빠름 (평균적으로)
- divide & conquer 알고리즘
- 재귀 사용
- 대부분 정렬 라이브러리의 기반

---

# 코테 현실 (⭐⭐⭐⭐⭐ 매우 중요)

퀵정렬은:

- divide & conquer 사고 테스트용
- 재귀 이해도 테스트
- partition 로직 이해 여부 테스트

👉 정렬 문제보다 “알고리즘 사고력” 확인용

---

# 실전에서는?

Python에서는 보통

```python
sorted(array)
```

사용.

하지만 퀵정렬 **직접 구현 이해는 필수**.
