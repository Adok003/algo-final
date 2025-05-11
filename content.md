
# 📘 Topic: Number Theory and Modular Arithmetic

## 🧠 Overview

Modular arithmetic, often referred to as "clock arithmetic," is a system where numbers wrap around after reaching a certain value, known as the modulus. This concept is fundamental in various fields, including cryptography, computer science, and number theory.

In modular arithmetic, two integers `a` and `b` are said to be congruent modulo `n` if their difference is divisible by `n`. This is denoted as:

```
a ≡ b (mod n)
```

This means that when `a` is divided by `n`, it leaves the same remainder as when `b` is divided by `n`.

---

## 🔢 Modular Operations

### Modular Addition

To perform addition under a modulus:

```
(a + b) mod m = ((a mod m) + (b mod m)) mod m
```

**Example:**
```
(15 + 17) mod 7 = ((15 mod 7) + (17 mod 7)) mod 7 = (1 + 3) mod 7 = 4
```

### Modular Subtraction

Subtraction under a modulus follows a similar pattern:

```
(a - b) mod m = ((a mod m) - (b mod m) + m) mod m
```

**Example:**
```
(15 - 17) mod 7 = ((15 mod 7) - (17 mod 7) + 7) mod 7 = (1 - 3 + 7) mod 7 = 5
```

### Modular Multiplication

Multiplication under a modulus is performed as:

```
(a × b) mod m = ((a mod m) × (b mod m)) mod m
```

**Example:**
```
(12 × 13) mod 5 = ((12 mod 5) × (13 mod 5)) mod 5 = (2 × 3) mod 5 = 1
```

### Modular Division

Division in modular arithmetic is not as straightforward. To divide `a` by `b` modulo `m`, we multiply `a` by the modular inverse of `b` modulo `m`:

```
(a / b) mod m = (a × b⁻¹) mod m
```

`b⁻¹` is the modular inverse of `b` modulo `m`, and it exists only if `gcd(b, m) = 1`.

---

## 📐 GCD and LCM

### Greatest Common Divisor (GCD)

The GCD of two integers is the largest integer that divides both without leaving a remainder. The Euclidean algorithm efficiently computes the GCD:

```python
def gcd(a, b):
    while b:
        a, b = b, a % b
    return a
```

### Least Common Multiple (LCM)

The LCM of two integers is the smallest positive integer that is divisible by both. It can be calculated using the GCD:

```python
def lcm(a, b):
    return a * b // gcd(a, b)
```

---

## 🔐 Modular Inverse and Cryptography

### Modular Inverse

The modular inverse of `a` modulo `m` is an integer `x` such that:

```
(a × x) mod m = 1
```

This inverse exists only if `a` and `m` are coprime. It can be computed using the Extended Euclidean Algorithm:

```python
def modinv(a, m):
    g, x, _ = extended_gcd(a, m)
    if g != 1:
        raise Exception('Modular inverse does not exist')
    return x % m

def extended_gcd(a, b):
    if b == 0:
        return a, 1, 0
    g, y, x = extended_gcd(b, a % b)
    return g, x, y - (a // b) * x
```

In cryptography, modular inverses are crucial for algorithms like RSA, where they are used to compute the private key from the public key.

---

## 🧮 Primality and Applications

### Prime Numbers

A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself. Primality tests, such as the Miller-Rabin test, are used to check if a number is prime, which is essential in cryptographic applications.

### Fermat's Little Theorem

If `p` is prime and `a` is an integer not divisible by `p`, then:

```
a^(p−1) ≡ 1 (mod p)
```

This theorem is used to compute modular inverses when the modulus is prime:

```
a^(-1) ≡ a^(p−2) (mod p)
```

---

## 🔐 RSA Cryptography Example

1. Choose two large prime numbers, `p` and `q`
2. Compute `n = p × q`
3. Compute Euler's totient function: `ϕ(n) = (p−1) × (q−1)`
4. Choose an integer `e` such that `1 < e < ϕ(n)` and `gcd(e, ϕ(n)) = 1`
5. Comoute the modular inverse of `e` module `ϕ(n)`, denotes as `d` : `d ≡ e⁻¹ mod ϕ(n)`
6. Public key: `(e, n)`, Private key: `(d, n)`

**Encrypt:**

```
ciphertext = (plaintext^e) mod n
```

**Decrypt:**

```
plaintext = (ciphertext^d) mod n
```

The security of RSA relies on the difficulty of factoring large composite numbers.

---

## ⚙️ Common Use Cases

| Problem Type         | Technique Used          | Notes                              |
|----------------------|-------------------------|------------------------------------|
| Cryptography         | Modular inverse, primes | RSA, Diffie-Hellman, ECC           |
| Scheduling           | LCM                     | Aligning periodic events           |
| Hashing              | Modular arithmetic      | Hash functions for data structures |
| Number puzzles       | GCD                     | Simplifying ratios                 |
| Combinatorics        | Fermat’s theorem        | Modulo division under prime mod    |

---

## 🧩 Key Takeaways

- Modular arithmetic wraps numbers within a defined range (modulus).
- Modular addition, subtraction, and multiplication are straightforward.
- Division requires computing the modular inverse, which only exists under certain conditions.
- GCD and LCM are fundamental in number theory and modular math.
- Cryptographic systems like RSA rely on these concepts for secure communication.
