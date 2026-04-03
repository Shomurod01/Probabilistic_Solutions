# Task 6 — Binomial Model

## Useful Definitions and Formulas

### 1. Binomial Distribution
A random variable \( X \) follows a binomial distribution if:
- There are \( n \) independent trials,
- Each trial has two outcomes: success or failure,
- The probability of success is constant \( p \).

\[
X \sim \text{Binomial}(n, p)
\]

---

### 2. Binomial Probability Formula

$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n - k}
$$

---

### 3. Complement Rule

$$
P(\text{at least one success}) = 1 - P(\text{no successes})
$$

---

# Given

- Probability of a defective part:

$$
p = 0.04
$$

- Number of inspected parts:

$$
n = 10
$$

Let:
- \( X \) = number of defective parts

Then:

$$
X \sim \text{Binomial}(10, 0.04)
$$

---

# Solutions

## 1. Probability that exactly 2 parts are defective

Using the binomial formula:

$$
P(X = 2) = \binom{10}{2} (0.04)^2 (0.96)^8
$$

Compute components:

$$
\binom{10}{2} = 45
$$

$$
(0.04)^2 = 0.0016
$$

$$
(0.96)^8 \approx 0.72139
$$

Now multiply:

$$
P(X = 2) \approx 45 \cdot 0.0016 \cdot 0.72139
$$

$$
P(X = 2) \approx 0.0519
$$

**Answer:** approximately \( 0.052 \)

---

## 2. Probability that at least one part is defective

Use the complement rule:

$$
P(X \ge 1) = 1 - P(X = 0)
$$

Compute:

$$
P(X = 0) = \binom{10}{0} (0.04)^0 (0.96)^{10}
$$

$$
P(X = 0) = (0.96)^{10}
$$

Approximate:

$$
(0.96)^{10} \approx 0.665
$$

Thus:

$$
P(X \ge 1) = 1 - 0.665 = 0.335
$$

**Answer:** approximately \( 0.335 \)

---
