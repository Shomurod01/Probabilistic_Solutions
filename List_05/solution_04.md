# Probability Distributions: Geometric & Poisson
 
> A complete step-by-step guide covering theory, formulas, probability calculations, and real-world applications.
 
---
 
## Table of Contents
 
- [Task 4 — Geometric Distribution](#task-4--geometric-distribution)
  - [1. The Experiment](#1-the-experiment)
  - [2. PMF and CDF Formulas](#2-pmf-and-cdf-formulas)
  - [3. Support and Why It Is Infinite](#3-support-and-why-it-is-infinite)
  - [4. PMF Shape for Different Values of p](#4-pmf-shape-for-different-values-of-p)
  - [5. CDF Shape for Different Values of p](#5-cdf-shape-for-different-values-of-p)
  - [6. How the Graphs Change with p](#6-how-the-graphs-change-with-p)
  - [7. Computing Probabilities](#7-computing-probabilities)
  - [8. Tail Probabilities and Waiting Time](#8-tail-probabilities-and-waiting-time)
  - [9. Practical Applications](#9-practical-applications)
- [Task 5 — Poisson Distribution](#task-5--poisson-distribution)
  - [1. The Experiment](#1-the-experiment-1)
  - [2. PMF Formula and Parameter](#2-pmf-formula-and-parameter)
  - [3. Support](#3-support)
  - [4. PMF Shape for Different Values of λ](#4-pmf-shape-for-different-values-of-λ)
  - [5. CDF Shape for Different Values of λ](#5-cdf-shape-for-different-values-of-λ)
  - [6. How Shape Changes as λ Increases](#6-how-shape-changes-as-λ-increases)
  - [7. Computing Probabilities](#7-computing-probabilities-1)
  - [8. CDF vs Direct Summation](#8-cdf-vs-direct-summation)
  - [9. Practical Applications](#9-practical-applications-1)
- [Side-by-Side Comparison](#side-by-side-comparison)
---
 
# Task 4 — Geometric Distribution
 
## 1. The Experiment
 
**Scenario:** You repeat the same experiment over and over. Each trial has exactly two outcomes — **success** (with probability `p`) or **failure** (with probability `1 − p`). Trials are independent. You stop the moment you get the **first success** and record how many trials it took.
 
**Concrete example:** Flip a possibly unfair coin repeatedly until the first Heads. Each flip is independent with P(Heads) = p.
 
### Formal Setup
 
| Element | Description |
|---|---|
| **Sample space Ω** | All sequences of failures ending in one success: `{S, FS, FFS, FFFS, …}` |
| **Elementary outcome ω** | A specific sequence, e.g. `ω = FFFS` means "failed 3 times, then succeeded on trial 4" |
| **Random variable X(ω)** | The trial number on which the first success occurs → `X(FFFS) = 4` |
 
> **Key idea:** Every elementary outcome ω is a string of F's (failures) followed by exactly one S (success). The random variable X simply counts the length of that string.
 
### Conditions Required
 
1. Each trial is **independent** — the result of one trial does not affect any other.
2. The probability of success `p` is **constant** across all trials.
3. You run trials **until the first success** — you do not fix the number of trials in advance.
---
 
## 2. PMF and CDF Formulas
 
### Probability Mass Function (PMF)
 
The PMF gives the probability that the first success occurs on **exactly** trial `k`:
 
```
P(X = k) = (1 − p)^(k−1) · p        for k = 1, 2, 3, …
```
 
**Why does this formula work?**
 
- You must **fail** on trials 1, 2, …, k−1 → probability `(1 − p)^(k−1)`
- You must **succeed** on trial k → probability `p`
- Since trials are independent, multiply: `(1 − p)^(k−1) · p`
**Example:** With p = 0.3, what is P(X = 4)?
 
```
P(X = 4) = (1 − 0.3)^(4−1) · 0.3
          = (0.7)^3 · 0.3
          = 0.343 · 0.3
          = 0.1029
```
 
So there is about a **10.3% chance** the first success happens on the 4th trial.
 
### Cumulative Distribution Function (CDF)
 
The CDF gives the probability that the first success occurs **on or before** trial `k`:
 
```
P(X ≤ k) = 1 − (1 − p)^k
```
 
**Why does this formula work?**
 
The only way X > k is if **all k trials failed**, which has probability `(1 − p)^k`. So:
 
```
P(X ≤ k) = 1 − P(X > k) = 1 − (1 − p)^k
```
 
**Example:** With p = 0.3, what is P(X ≤ 4)?
 
```
P(X ≤ 4) = 1 − (0.7)^4 = 1 − 0.2401 = 0.7599
```
 
So there is about a **76% chance** of getting the first success within 4 trials.
 
### Key Statistics
 
| Statistic | Formula | Meaning |
|---|---|---|
| Mean (Expected value) | `E[X] = 1/p` | Average number of trials until first success |
| Variance | `Var(X) = (1−p) / p²` | Spread around the mean |
| Standard deviation | `SD(X) = √((1−p)/p²)` | Typical deviation from the mean |
| Mode | `1` | Most likely trial for first success |
 
**Example with p = 0.3:**
 
```
E[X]   = 1 / 0.3 ≈ 3.33  trials on average
Var(X) = 0.7 / 0.09 ≈ 7.78
SD(X)  ≈ 2.79
```
 
---
 
## 3. Support and Why It Is Infinite
 
The **support** of a distribution is the set of values the random variable can take.
 
For the geometric distribution:
 
```
Support = {1, 2, 3, 4, 5, …}
```
 
**Why does it start at 1?**
You cannot have "zero trials" — you must perform at least one trial to get a result.
 
**Why is it infinite?**
There is no maximum number of trials. In theory, you could fail on every trial forever. For any integer k, no matter how large, the probability `(1 − p)^(k−1) · p` is positive (as long as p < 1). So every positive integer is a possible value of X.
 
> **Intuition:** Imagine flipping a fair coin until Heads. You might get Heads on flip 1, or flip 10, or flip 1000. There is no upper limit — you just keep going until it happens.
 
---
 
## 4. PMF Shape for Different Values of p
 
Below are PMF values for `k = 1` through `k = 10` for several values of `p`:
 
| k | p = 0.10 | p = 0.30 | p = 0.50 | p = 0.80 |
|---|---|---|---|---|
| 1 | 0.1000 | 0.3000 | 0.5000 | 0.8000 |
| 2 | 0.0900 | 0.2100 | 0.2500 | 0.1600 |
| 3 | 0.0810 | 0.1470 | 0.1250 | 0.0320 |
| 4 | 0.0729 | 0.1029 | 0.0625 | 0.0064 |
| 5 | 0.0656 | 0.0720 | 0.0313 | 0.0013 |
| 6 | 0.0590 | 0.0504 | 0.0156 | 0.0003 |
| 7 | 0.0531 | 0.0353 | 0.0078 | ~0 |
| 8 | 0.0478 | 0.0247 | 0.0039 | ~0 |
| 9 | 0.0430 | 0.0173 | 0.0020 | ~0 |
| 10 | 0.0387 | 0.0121 | 0.0010 | ~0 |
 
**Observations:**
- The bar at `k = 1` always equals `p` exactly.
- All distributions are **right-skewed** (long tail to the right).
- Higher `p` → taller first bar, steeper drop-off.
- Lower `p` → lower first bar, slower decay, longer tail.
---
 
## 5. CDF Shape for Different Values of p
 
| k | p = 0.10 | p = 0.30 | p = 0.50 | p = 0.80 |
|---|---|---|---|---|
| 1 | 0.1000 | 0.3000 | 0.5000 | 0.8000 |
| 2 | 0.1900 | 0.5100 | 0.7500 | 0.9600 |
| 3 | 0.2710 | 0.6570 | 0.8750 | 0.9920 |
| 5 | 0.4095 | 0.8319 | 0.9688 | ~1.000 |
| 10 | 0.6513 | 0.9718 | 0.9990 | ~1.000 |
| 20 | 0.8784 | 0.9992 | ~1.000 | ~1.000 |
 
**Observations:**
- The CDF is a **staircase function** that increases and approaches 1.
- It reaches 1 asymptotically — it never quite equals 1 for any finite k.
- Higher `p` → the CDF reaches near 1 much faster.
---
 
## 6. How the Graphs Change with p
 
### When p is large (e.g. p = 0.8)
 
- The PMF has a **tall spike at k = 1** and drops off very sharply.
- Interpretation: you almost always succeed on the first try.
- The mean is small: `E[X] = 1/0.8 = 1.25 trials`.
- The CDF reaches near 1 after just 3–4 trials.
### When p is small (e.g. p = 0.1)
 
- The PMF has a **low first bar** and decays slowly — a long flat tail.
- Interpretation: you often wait many trials for the first success.
- The mean is large: `E[X] = 1/0.1 = 10 trials`.
- The CDF reaches near 1 only after 20–30+ trials.
### Summary
 
| p | Shape | Mean | Behaviour |
|---|---|---|---|
| Large (close to 1) | Steep drop from k=1 | Close to 1 | Success comes quickly |
| Medium (0.3–0.5) | Moderate decay | 2–3 trials | Moderate waiting time |
| Small (close to 0) | Slow decay, long tail | Many trials | Long waiting time |
 
---
 
## 7. Computing Probabilities
 
### Four Key Probability Types
 
#### P(X = k) — Exactly k trials
 
```
P(X = k) = (1 − p)^(k−1) · p
```
 
**Example** (p = 0.3, k = 5):
```
P(X = 5) = (0.7)^4 · 0.3 = 0.2401 · 0.3 = 0.0720  →  7.20%
```
 
#### P(X ≤ k) — At most k trials (CDF)
 
```
P(X ≤ k) = 1 − (1 − p)^k
```
 
**Example** (p = 0.3, k = 5):
```
P(X ≤ 5) = 1 − (0.7)^5 = 1 − 0.1681 = 0.8319  →  83.19%
```
 
#### P(X > k) — More than k trials (survival function)
 
```
P(X > k) = (1 − p)^k
```
 
**Example** (p = 0.3, k = 5):
```
P(X > 5) = (0.7)^5 = 0.1681  →  16.81%
```
 
#### P(a ≤ X ≤ b) — Between a and b trials
 
```
P(a ≤ X ≤ b) = P(X ≤ b) − P(X ≤ a−1)
              = (1 − p)^(a−1) − (1 − p)^b
```
 
**Example** (p = 0.3, a = 3, b = 6):
```
P(3 ≤ X ≤ 6) = (0.7)^2 − (0.7)^6
              = 0.4900 − 0.1176
              = 0.3724  →  37.24%
```
 
### Quick Reference Table (p = 0.3)
 
| Probability | k = 3 | k = 5 | k = 10 |
|---|---|---|---|
| P(X = k) | 14.70% | 7.20% | 1.21% |
| P(X ≤ k) | 65.70% | 83.19% | 97.18% |
| P(X > k) | 34.30% | 16.81% | 2.82% |
 
---
 
## 8. Tail Probabilities and Waiting Time
 
The **tail probability** P(X > k) = (1 − p)^k answers the question:
 
> "What is the chance I still have not succeeded after k trials?"
 
### Numerical Examples
 
With **p = 0.1** (a hard problem — only 10% chance per trial):
 
| After k trials | P(still no success) |
|---|---|
| k = 5 | (0.9)^5 = 59.0% |
| k = 10 | (0.9)^10 = 34.9% |
| k = 20 | (0.9)^20 = 12.2% |
| k = 30 | (0.9)^30 = 4.2% |
| k = 50 | (0.9)^50 = 0.5% |
 
### The Memoryless Property
 
The geometric distribution is the **only discrete distribution** with the memoryless property:
 
```
P(X > m + n | X > m) = P(X > n)
```
 
**In plain language:** If you have already failed m times, the probability of needing more than n additional trials is exactly the same as if you were starting fresh. Past failures give you **no information** about when the first success will come.
 
> **Example:** You are flipping a coin with p = 0.3. You have already failed 10 times. The probability of needing more than 5 more flips is still (0.7)^5 = 16.8% — exactly the same as at the very beginning.
 
This makes geometric a natural model for **waiting times** in situations with no memory (electronic components, network transmissions, coin flips).
 
---
 
## 9. Practical Applications
 
| Application | What X represents | Typical p |
|---|---|---|
| Job searching | Number of applications until first offer | 0.05–0.20 |
| Sales | Number of calls until first sale | 0.10–0.30 |
| Network | Number of packet transmissions until acknowledged | 0.80–0.99 |
| Quality control | Number of items inspected until first defect | 0.001–0.05 |
| Medicine | Number of patients tested until first positive response | 0.10–0.50 |
| Gaming | Number of attempts until first win | varies |
| Biology | Number of cell divisions until first mutation | very small |
| Cryptography | Number of hash attempts until first collision | very small |
 
---
