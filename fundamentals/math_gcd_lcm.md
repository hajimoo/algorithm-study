# math.gcd & LCM

최대공약수(GCD): `math.gcd(a, b)`  
최소공배수(LCM): `a*b // gcd(a,b)`

```python
import math

def lcm(a, b):
    return a * b // math.gcd(a, b)

a = 21
b = 14

print(math.gcd(a, b))  # GCD
print(lcm(a, b))       # LCM
✅ 언제 쓰나?

비율/주기/나눗셈/약수 문제
