# GCD & LCM

> EN Summary: Use math.gcd for greatest common divisor. LCM = a*b // gcd(a,b).

---

## 코드

```python
import math

def lcm(a, b):
    return a * b // math.gcd(a, b)

a = 21
b = 14

print(math.gcd(a, b))
print(lcm(a, b))
```

---

## 시간복잡도

- gcd: O(log N)
