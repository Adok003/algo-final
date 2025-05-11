
## Question 1

**Q**: What does `a ≡ b (mod m)` mean in modular arithmetic?

**A**: It means that `(a - b)` is divisible by `m`, or equivalently, `a` and `b` leave the same remainder when divided by `m`.

---

## Question 2

**Q**: When does a modular inverse exist for an integer `a` modulo `m`?

**A**: A modular inverse exists if and only if `a` and `m` are coprime, i.e., `gcd(a, m) = 1`.

---

## Question 3

**Q**: How can you compute a modular inverse when `m` is a prime number?

**A**: Use Fermat’s Little Theorem: `a^(-1) ≡ a^(m−2) mod m`, assuming `a` is not divisible by `m`.

---

## Question 4

**Q**: What is the formula for computing LCM using GCD?

**A**: `lcm(a, b) = (a * b) / gcd(a, b)`

---

## Question 5

**Q**: Why is modular exponentiation preferred in cryptographic applications?

**A**: It efficiently computes large powers under a modulus, prevents overflow, and is essential for algorithms like RSA.
