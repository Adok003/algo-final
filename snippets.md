
## Snippet 1: Modular Arithmetic

Modular arithmetic deals with integers and remainders. It's used in hashing, cryptography, and clock calculations.

```python
print(17 % 5)  # Output: 2
```

---

## Snippet 2: Euclidean Algorithm for GCD

Finds the greatest common divisor efficiently using repeated division.

```python
def gcd(a, b):
    while b:
        a, b = b, a % b
    return a
```

---

## Snippet 3: Least Common Multiple (LCM)

LCM is calculated using the GCD of two numbers: `lcm(a, b) = (a * b) // gcd(a, b)`

```python
def lcm(a, b):
    return a * b // gcd(a, b)
```

---

## Snippet 4: Modular Inverse

If `a` and `m` are coprime, the modular inverse `x` satisfies `a * x ≡ 1 (mod m)`.

```python
def modinv(a, m):
    return pow(a, -1, m)
```

---

## Snippet 5: Fermat’s Little Theorem

If `p` is prime, then `a^(p−1) ≡ 1 mod p` helps compute modular inverses.

```python
def inverse(a, p):
    return pow(a, p - 2, p)
```

---

## Snippet 6: Extended Euclidean Algorithm

It provides coefficients `x, y` such that `ax + by = gcd(a, b)`.

```python
def extended_gcd(a, b):
    if b == 0:
        return a, 1, 0
    g, x1, y1 = extended_gcd(b, a % b)
    return g, y1, x1 - (a // b) * y1
```

---

## Snippet 7: Prime Check (Naive)

Checks if a number is prime using trial division.

```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True
```

---

## Snippet 8: Modular Exponentiation

Efficiently compute `a^b mod m` using exponentiation by squaring.

```python
def modexp(a, b, m):
    result = 1
    a %= m
    while b > 0:
        if b % 2:
            result = (result * a) % m
        a = (a * a) % m
        b //= 2
    return result
```
