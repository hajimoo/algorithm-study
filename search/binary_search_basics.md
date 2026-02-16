# Binary Search (이진 탐색)

> EN Summary: Binary search finds a target in a sorted array by repeatedly halving the search range. Time complexity O(log N).

---

## Search Types

### Sequential Search (순차 탐색)

- Check elements one by one from the beginning
- Time complexity: O(N)

---

### Binary Search (이진 탐색)

- Works only on **sorted arrays**
- Repeatedly halves the search range
- Uses:
  - start index
  - end index
  - middle index

---

## How Binary Search Works

Example sorted array:

```
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```

Find value = 4

---

### Step 1

```
start = 0
end = 9
mid = 4
value = 8
```

Target < mid → search left

---

### Step 2

```
start = 0
end = 3
mid = 1
value = 2
```

Target > mid → search right

---

### Step 3

```
start = 2
end = 3
mid = 2
value = 4
```

Found.

---

## Time Complexity

Each step halves the search range.

Example:

```
32 elements → 16 → 8 → 4 → 2 → 1
```

So operations grow with:

```
log2(N)
```

Final complexity:

```
O(log N)
```

---

## Recursive Implementation (Python)

```python
def binary_search(array, target, start, end):
    if start > end:
        return None

    mid = (start + end) // 2

    if array[mid] == target:
        return mid

    elif array[mid] > target:
        return binary_search(array, target, start, mid - 1)

    else:
        return binary_search(array, target, mid + 1, end)
```

---

## Example Usage

```python
n, target = list(map(int, input().split()))
array = list(map(int, input().split()))

result = binary_search(array, target, 0, n - 1)

if result is None:
    print("Element not found")
else:
    print(result + 1)
```

---

## Iterative Implementation (Important for Coding Tests)

```python
def binary_search(array, target):
    start = 0
    end = len(array) - 1

    while start <= end:
        mid = (start + end) // 2

        if array[mid] == target:
            return mid

        elif array[mid] < target:
            start = mid + 1

        else:
            end = mid - 1

    return None
```

---

## When to Use Binary Search

✅ Data is sorted  
✅ Need fast lookup  
✅ Need O(log N) search  

---

## Notes (코테 핵심)

- 정렬 안 되어 있으면 binary search 사용 불가
- Python `bisect` 라이브러리도 매우 중요
- iterative 버전이 recursion보다 안전 (stack 문제 없음)
