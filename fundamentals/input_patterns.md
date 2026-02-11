# Input Patterns (Python)

## 기본 입력 패턴

### 데이터 개수
```python
n = int(input())
```

### 공백 구분 정수 리스트
```python
data = list(map(int, input().split()))
```

### 문자열을 split 후 정수 리스트
```python
input_data = input()
data = list(map(int, input_data.split()))
```

---

## 빠른 입력 (자주 암기)

입력이 많으면 `sys.stdin.readline()` 사용이 유리할 수 있음.

```python
import sys
input = sys.stdin.readline

line = input().rstrip()
```

---

## 체크 포인트

- `rstrip()`은 개행 제거용  
- `input = sys.stdin.readline`으로 치환하면 매번 타이핑 줄어듦  
