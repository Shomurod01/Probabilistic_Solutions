# Task 9 — Poisson Model

## Useful Definitions and Formulas

### 1. Poisson Distribution
A random variable \( X \) follows a Poisson distribution if it models the number of events occurring in a fixed interval of time or space.

\[
X \sim \text{Poisson}(\lambda)
\]

where:
- \( \lambda \) = average number of events in the interval.

---

### 2. Poisson Probability Formula

$$
P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}
$$

---

### 3. Complement Rule

$$
P(X \ge 1) = 1 - P(X = 0)
$$

---

# Given

- Average number of requests per hour:

$$
\lambda = 5
$$

Let \( X \) be the number of requests in one hour:

$$
X \sim \text{Poisson}(5)
$$

---

# Solutions

## 1. Probability that exactly 3 requests occur

Using the Poisson formula:

$$
P(X = 3) = \frac{5^3 e^{-5}}{3!}
$$

Compute components:

$$
5^3 = 125
$$

$$
3! = 6
$$

So:

$$
P(X = 3) = \frac{125 \cdot e^{-5}}{6}
$$

Approximate:

$$
e^{-5} \approx 0.006737
$$

$$
P(X = 3) \approx \frac{125 \cdot 0.006737}{6}
$$

$$
P(X = 3) \approx \frac{0.842125}{6} \approx 0.1404
$$

**Answer:** approximately \( 0.140 \)

---

## 2. Probability that at least one request occurs

Using the complement rule:

$$
P(X \ge 1) = 1 - P(X = 0)
$$

Compute:

$$
P(X = 0) = \frac{5^0 e^{-5}}{0!} = e^{-5}
$$

Thus:

$$
P(X \ge 1) = 1 - e^{-5}
$$

Approximate:

$$
P(X \ge 1) = 1 - 0.006737 = 0.9933
$$

**Answer:** approximately \( 0.993 \)

---
