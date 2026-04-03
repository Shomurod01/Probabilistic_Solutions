# Task 4 — Poisson Model (Arrival of Events)

## Useful Definitions and Formulas

### 1. Poisson Distribution
The Poisson distribution models the number of events occurring in a fixed interval of time or space when:
- Events occur independently,
- The average rate of occurrence is constant,
- Events occur one at a time.

---

### 2. Poisson Probability Formula

If \( X \sim \text{Poisson}(\lambda) \), then:

$$
P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}
$$

for:

$$
k = 0, 1, 2, \dots
$$

---

### 3. Parameter \( \lambda \)

- \( \lambda \) represents the **average number of events** in the given interval.
- It is both the mean and variance of the distribution.

---

# Given

- Average number of error reports per hour: 3  
- Therefore:

$$
\lambda = 3 \text{ per hour}
$$

---

# Solutions

## 1. Describe the random experiment

The experiment consists of:
- Observing a web service over a fixed time interval (e.g., one hour),
- Counting the number of error reports received during that interval,
- Assuming:
  - Error reports occur independently,
  - The average rate of occurrence is constant over time.

---

## 2. Determine the sample space \( \Omega \)

The random variable represents the number of error reports in the given interval.

Possible outcomes are all non-negative integers:

$$
\Omega = \{0, 1, 2, 3, 4, \dots\}
$$

---

## 3. Provide the formula of the probability distribution

Let \( X \) be the number of error reports in one hour. Then:

$$
X \sim \text{Poisson}(\lambda)
$$

with \( \lambda = 3 \), and the probability mass function is:

$$
P(X = k) = \frac{3^k e^{-3}}{k!}
$$

for:

$$
k = 0, 1, 2, \dots
$$

---

## 4. Interpret the parameter \( \lambda \) and explain its value for one hour

- The parameter \( \lambda \) represents the **expected (average) number of events** in the time interval.
- In this problem:
  - \( \lambda = 3 \) means that, on average, the system receives **3 error reports per hour**.

Interpretation:
- Over many hours, the average number of reports per hour will approach 3.
- It also implies:
  - Mean = 3
  - Variance = 3

---
