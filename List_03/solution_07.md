# Task 7 — Hypergeometric Model

## Useful Definitions and Formulas

### 1. Hypergeometric Distribution
Used when sampling **without replacement** from a finite population.

If:
- \( N \) = total number of items  
- \( K \) = number of defective (success) items  
- \( n \) = sample size  
- \( X \) = number of defective items in the sample  

Then:

$$
P(X = k) = \frac{\binom{K}{k}\binom{N - K}{n - k}}{\binom{N}{n}}
$$

---

# Given

- Total bulbs:

$$
N = 15
$$

- Defective bulbs:

$$
K = 3
$$

- Working bulbs:

$$
12
$$

- Sample size:

$$
n = 5
$$

We want:

$$
P(X = 2)
$$

---

# Solution

## Step 1: Apply the hypergeometric formula

$$
P(X = 2) = \frac{\binom{3}{2}\binom{12}{3}}{\binom{15}{5}}
$$

---

## Step 2: Compute each term

$$
\binom{3}{2} = 3
$$

$$
\binom{12}{3} = 220
$$

$$
\binom{15}{5} = 3003
$$

---

## Step 3: Substitute values

$$
P(X = 2) = \frac{3 \cdot 220}{3003}
$$

$$
P(X = 2) = \frac{660}{3003}
$$

---

## Step 4: Simplify

$$
\frac{660}{3003} = \frac{220}{1001}
$$

---

## Final Answer

$$
P(X = 2) = \frac{220}{1001} \approx 0.2198
$$
