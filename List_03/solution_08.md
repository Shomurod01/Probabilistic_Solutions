# Task 8 — Geometric Model

## Useful Definitions and Formulas

### 1. Geometric Distribution
The geometric distribution models the number of trials until the **first success** occurs.

If:
- Each trial has probability \( p \) of success,
- Trials are independent,

then:

$$
P(X = k) = (1 - p)^{k - 1} \cdot p
$$

for:

$$
k = 1, 2, 3, \dots
$$

---

# Given

- Probability of an error (success):

$$
p = 0.1
$$

- Probability of no error:

$$
1 - p = 0.9
$$

Let \( X \) = the number of the compilation on which the first error occurs.

---

# Solutions

## 1. Probability that the first error appears on the 4th compilation

Using the geometric formula:

$$
P(X = 4) = (1 - p)^{3} \cdot p
$$

Substitute values:

$$
P(X = 4) = (0.9)^3 \cdot 0.1
$$

Compute:

$$
(0.9)^3 = 0.729
$$

$$
P(X = 4) = 0.729 \cdot 0.1 = 0.0729
$$

**Answer:** \( 0.0729 \)

---

## 2. Probability that the first error appears no later than the 3rd compilation

This means:

$$
P(X \le 3) = P(X = 1) + P(X = 2) + P(X = 3)
$$

Compute each term:

$$
P(X = 1) = (0.9)^0 \cdot 0.1 = 0.1
$$

$$
P(X = 2) = (0.9)^1 \cdot 0.1 = 0.09
$$

$$
P(X = 3) = (0.9)^2 \cdot 0.1 = 0.081
$$

Sum:

$$
P(X \le 3) = 0.1 + 0.09 + 0.081 = 0.271
$$

**Answer:** \( 0.271 \)

---
