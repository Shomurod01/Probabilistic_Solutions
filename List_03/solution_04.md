# Task 4 — Poisson Model (Arrival of Events)

## 1. Description of the Random Experiment

We observe a web service over a fixed time interval (for example, one hour) and count the number of error reports received during that time.

- Each outcome of the experiment is the number of error reports observed.
- The experiment is random because the exact number of reports cannot be predicted in advance.

---

## 2. Sample Space \( \Omega \)

The number of error reports can be any non-negative integer.

$$
\Omega = \{0, 1, 2, 3, \dots\}
$$

This means:
- 0 reports,
- 1 report,
- 2 reports,
- and so on.

---

## 3. Probability Distribution Formula

The number of error reports follows a Poisson distribution.

The probability of observing exactly \( k \) reports is:

$$
P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \dots
$$

where:
- \( \lambda \) is the average number of events in the given time interval,
- \( e \approx 2.71828 \),
- \( k! \) is the factorial of \( k \).

---

## 4. Interpretation of the Parameter \( \lambda \)

The parameter \( \lambda \) represents the average (expected) number of error reports in a given time interval.

In this problem:

$$
\lambda = 3
$$

for one hour.

### Meaning:
- On average, the system receives **3 error reports per hour**.
- It does **not** mean exactly 3 reports every hour.
- Some hours may have:
  - fewer than 3 reports,
  - more than 3 reports.

### Key Property:
For a Poisson distribution:

$$
\mathbb{E}[X] = \lambda
$$

So the expected number of reports in one hour is:

$$
\mathbb{E}[X] = 3
$$

---

## Summary

- The experiment counts error reports in a fixed time interval.
- The sample space includes all non-negative integers.
- The distribution follows the Poisson formula.
- The parameter \( \lambda = 3 \) represents the average number of reports per hour.
