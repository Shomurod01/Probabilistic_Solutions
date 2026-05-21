# Geometric Distribution — Complete Guide

> **Goal:** Understand the geometric distribution from scratch — experiment, formula, graphs, probabilities, and real applications.

---

## 0. The Experiment

### Setup
Repeat independent **Bernoulli trials** (each trial: success with probability `p`, failure with probability `1-p`) **until the first success**.

### Sample Space Ω
$$\Omega = \{\text{S},\ \text{FS},\ \text{FFS},\ \text{FFFS},\ \ldots\}$$

Each element is a string of F's followed by one S.

### One Elementary Outcome ω
$$\omega = \text{FFS} \quad \Rightarrow \quad \text{fail, fail, success on trial 3}$$

### Random Variable X(ω)
$$X(\omega) = \text{number of the trial on which the first success occurs}$$

For the example above: $X(\text{FFS}) = 3$

---

## 1. PMF and CDF

### Probability Mass Function (PMF)
$$\boxed{P(X = k) = (1-p)^{k-1} \cdot p}, \quad k = 1, 2, 3, \ldots$$

**Why?** To get the first success on trial $k$, you need $(k-1)$ failures **then** 1 success.

| Factor | Meaning |
|--------|---------|
| $(1-p)^{k-1}$ | probability of $(k-1)$ consecutive failures |
| $p$ | probability of success on trial $k$ |

### Cumulative Distribution Function (CDF)
$$\boxed{F(k) = P(X \leq k) = 1 - (1-p)^k}, \quad k = 1, 2, 3, \ldots$$

**Derivation:**
$$P(X \leq k) = 1 - P(X > k) = 1 - P(\text{first } k \text{ trials all fail}) = 1 - (1-p)^k$$

---

## 2. Support and Why It Is Infinite

### Support
$$\text{Support} = \{1, 2, 3, 4, \ldots\} = \mathbb{Z}^+$$

### Why Infinite?

There is **no upper bound** on how long you might wait for the first success.

- No matter how many failures you've had, another failure is always possible.
- For any $k$, there is a positive probability $P(X = k) = (1-p)^{k-1} p > 0$.
- Therefore the distribution cannot stop at any finite value.

> **Intuition:** Even with $p = 0.99$, there's a chance the first success comes on trial 1,000,000.

---

## 3. PMF Graphs for Several Values of p

```
P(X=k)
 0.8 |*                          p = 0.8
     | *
 0.4 |  *
     |   * *
 0.1 |       * * * * * * ...
     +-------------------------> k
       1  2  3  4  5  6

 0.4 |*                          p = 0.4
     | *
 0.2 |  *
     |   *  *
 0.1 |      *  *  *  * ...
     +-------------------------> k
       1  2  3  4  5  6

 0.1 |*                          p = 0.1
     |*
     |*
     |*  *  *  *  *  *  * ...
     +-------------------------> k
       1  2  3  4  5  6
```

**Key shape:** Always starts at $p$ when $k=1$, then **decreases exponentially** (geometric decay).

---

## 4. CDF Graphs for the Same Values of p

```
F(k) = P(X ≤ k)

 1.0 |         * * * * * *      p = 0.8  (rises fast)
     |      *
 0.5 |   *
     |  *
     | *
 0.0 +-------------------------> k
       1  2  3  4  5  6

 1.0 |               * * * *   p = 0.4  (medium rise)
     |         *
 0.5 |      *
     |   *
     | *
 0.0 +-------------------------> k
       1  2  3  4  5  6

 1.0 |                    * *  p = 0.1  (rises slowly)
     |               *
 0.5 |         *
     |      *
     | *
 0.0 +-------------------------> k
       1  2  3  4  5  6
```

**Key shape:** Starts near $p$ at $k=1$, increases toward 1, **never reaches 1** exactly at any finite $k$.

---

## 5. How Graphs Change with p

| p larger (closer to 1) | p smaller (closer to 0) |
|------------------------|------------------------|
| PMF drops off **quickly** | PMF drops off **slowly** |
| PMF bar at $k=1$ is **tall** | PMF bar at $k=1$ is **short** |
| CDF reaches near 1 **fast** | CDF climbs toward 1 **slowly** |
| You expect success **soon** | You expect to **wait long** |

### Summary Rule
> **Larger p → shorter waiting time → steeper PMF → faster-rising CDF**

---

## 6. Computing Probabilities

### P(X = k) — exact trial
$$P(X = k) = (1-p)^{k-1} \cdot p$$

**Example** ($p = 0.3, k = 4$):
$$P(X=4) = (0.7)^3 \cdot 0.3 = 0.343 \cdot 0.3 = 0.1029$$

---

### P(X ≤ k) — success by trial k
$$P(X \leq k) = 1 - (1-p)^k$$

**Example** ($p = 0.3, k = 4$):
$$P(X \leq 4) = 1 - (0.7)^4 = 1 - 0.2401 = 0.7599$$

---

### P(X > k) — still waiting after k trials
$$P(X > k) = (1-p)^k$$

**Example** ($p = 0.3, k = 4$):
$$P(X > 4) = (0.7)^4 = 0.2401$$

---

### P(a ≤ X ≤ b) — success falls in a window
$$P(a \leq X \leq b) = P(X \leq b) - P(X \leq a-1) = (1-p)^{a-1} - (1-p)^b$$

**Example** ($p = 0.3, a = 3, b = 6$):
$$P(3 \leq X \leq 6) = (0.7)^2 - (0.7)^6 = 0.49 - 0.1176 = 0.3724$$

---

## 7. Interpreting Tail Probabilities

$$P(X > k) = (1-p)^k$$

This is the probability that **you are still waiting** after $k$ trials — the system has not yet succeeded.

### Memoryless Property
$$P(X > m + n \mid X > m) = P(X > n)$$

> **Meaning:** If you've already failed $m$ times, the probability of waiting $n$ more trials is **exactly the same** as if you had just started. The past doesn't matter.

### Practical Reading of Tail Probabilities

| Situation | Probability | Interpretation |
|-----------|-------------|----------------|
| Waiting time exceeds 5 | $(1-p)^5$ | 5 attempts weren't enough |
| Waiting time exceeds 10 | $(1-p)^{10}$ | Very unlucky streak |
| Waiting time exceeds 20 | $(1-p)^{20}$ | Extremely rare (small for any $p > 0$) |

---

## 8. Practical Applications

| Application | X = ? | p = ? |
|-------------|-------|-------|
| **Quality control** | Number of items tested until a defective one is found | defect rate |
| **Clinical trials** | Number of patients enrolled until first adverse event | event probability |
| **Network packets** | Number of transmission attempts until first success | success probability per attempt |
| **Coin flipping game** | Number of flips until first heads | 0.5 |
| **Sales calls** | Number of calls until first sale | conversion rate |
| **Drilling for oil** | Number of wells drilled until first strike | success rate per well |
| **Cybersecurity** | Number of login attempts until first breach | per-attempt success probability |

### Why Geometric?
Use the geometric model whenever:
1. Trials are **independent**
2. Each trial has **the same probability p** of success
3. You care about **when** the first success happens

---

## 9. Geometric in the Discrete Distribution Family

| Property | Geometric | Binomial | Poisson |
|----------|-----------|----------|---------|
| **Counts** | trials until 1st success | successes in $n$ trials | events in time/space |
| **Support** | $\{1, 2, 3, \ldots\}$ | $\{0, 1, \ldots, n\}$ | $\{0, 1, 2, \ldots\}$ |
| **Parameter(s)** | $p$ | $n, p$ | $\lambda$ |
| **Mean** | $1/p$ | $np$ | $\lambda$ |
| **Variance** | $(1-p)/p^2$ | $np(1-p)$ | $\lambda$ |
| **Memoryless?** | ✅ Yes | ❌ No | ❌ No |
| **Infinite support?** | ✅ Yes | ❌ No | ✅ Yes |

> The geometric distribution is the **only discrete memoryless distribution** — a unique and important property.

---

## Quick Reference Card

$$P(X=k) = (1-p)^{k-1}p \qquad P(X \leq k) = 1-(1-p)^k \qquad P(X>k) = (1-p)^k$$

$$E[X] = \frac{1}{p} \qquad \text{Var}(X) = \frac{1-p}{p^2}$$

$$\text{Support: } k \in \{1, 2, 3, \ldots\} \qquad \text{Memoryless: } P(X>m+n \mid X>m) = P(X>n)$$
