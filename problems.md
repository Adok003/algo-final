
## Problem 1: GCD of Array

**Problem Statement**  
Given an array of integers, find the greatest common divisor (GCD) of all the elements.  
Example: Input: [12, 18, 24] → Output: 6

---

### 🔹 Hints
1. Hint 1: Use the gcd of the first two elements, then apply it iteratively.
2. Hint 2: Euclidean algorithm helps here.

### 🔹 Brute Force Idea  
Try all numbers from 1 to the minimum element and check which one divides all elements.

---

### 🔹 Optimized Idea  
Use the built-in `gcd` function iteratively over the array using `reduce`.

---

### 🔹 Code Fragment
```python
from math import gcd
from functools import reduce

def gcd_of_array(arr):
    return reduce(gcd, arr)
```

---

## Problem 2: Modular Inverse

**Problem Statement**  
Find the modular inverse of `a` under modulo `m`, if it exists.  
Example: Input: a = 3, m = 11 → Output: 4 (because 3×4 ≡ 1 mod 11)

---

### 🔹 Hints
1. Hint 1: Use Fermat’s Little Theorem if `m` is prime.
2. Hint 2: Use the extended Euclidean algorithm otherwise.

### 🔹 Brute Force Idea  
Try every number from 1 to m−1 to see which satisfies `(a * x) % m == 1`.

---

### 🔹 Optimized Idea  
Use `pow(a, m-2, m)` for primes or extended Euclidean for general case.

---

### 🔹 Code Fragment
```python
def modinv(a, m):
    return pow(a, m - 2, m)  # Only works if m is prime
```

---

## Problem 3: LCM of Two Numbers

**Problem Statement**  
Given two integers, find their least common multiple (LCM).  
Example: Input: a = 6, b = 8 → Output: 24

---

### 🔹 Hints
1. Hint 1: First find the GCD.
2. Hint 2: Use the LCM formula.

### 🔹 Brute Force Idea  
Increment the larger number until it’s divisible by the smaller.

---

### 🔹 Optimized Idea  
Use `lcm(a, b) = (a * b) // gcd(a, b)`.

---

### 🔹 Code Fragment
```python
def lcm(a, b):
    from math import gcd
    return a * b // gcd(a, b)
```
