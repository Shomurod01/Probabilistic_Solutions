# Task 4 — Poisson Model (Arrival of Events)

## 1. Random Experiment
The random experiment consists of **counting the number of error reports received by a web service during a fixed time interval** (one hour).  
- The web service operates under stable conditions.  
- Errors occur randomly over time, independently of each other.  
- The average rate of errors is constant: 3 per hour.  
- Only the total count in the interval is observed, not the exact arrival times.

## 2. Sample Space (\(\Omega\))
The sample space is the set of all possible outcomes (non‑negative integers):  
\[
\Omega = \{0, 1, 2, 3, \dots\}
\]  
(There is no theoretical upper bound, though very large numbers are extremely unlikely.)

## 3. Probability Distribution Formula
Let \(X\) be the number of error reports in one hour. Under the Poisson assumptions,  
\[
P(X = k) = \frac{e^{-\lambda} \cdot \lambda^{k}}{k!}, \qquad k = 0, 1, 2, \dots
\]  
where:
- \(e \approx 2.71828\) (Euler’s number)
- \(k!\) is the factorial of \(k\)
- \(\lambda\) is the parameter of the distribution.

## 4. Interpretation of \(\lambda\) and Its Value for One Hour
- **Interpretation:** \(\lambda\) is the **average (mean) number of events** occurring in the given time interval. It also equals the variance in a Poisson distribution. In a Poisson process, \(\lambda = \text{rate} \times \text{time interval length}\).

- **Value for one hour:**  
  The problem states that the web service receives **on average 3 error reports per hour**. Therefore, for a one‑hour interval,  
  \[
  \lambda = 3
  \]  
  This means that over many one‑hour observations, the average number of reports would be 3. The probability of exactly \(k\) reports in one hour becomes  
  \[
  P(X = k) = \frac{e^{-3} \cdot 3^{k}}{k!}.
  \]
