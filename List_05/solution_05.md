# Poisson Distribution — Complete Guide

> **Goal:** Understand the Poisson distribution — experiment, formula, graphs, probabilities, and real applications.

---

## 1. The Experiment

### Setup
Count the number of **random events** occurring in a **fixed interval** (time, space, length, area), where:
- Events occur **independently** of each other
- Events occur at a **constant average rate** λ (lambda)
- Two events cannot occur at **exactly the same instant**

### Example Experiment
Count the number of **customers arriving at a coffee shop in one hour**.

### Sample Space Ω
$$\Omega = \{0, 1, 2, 3, \ldots\}$$

Any non-negative integer is possible — in principle, infinitely many customers could arrive.

### One Elementary Outcome ω
$$\omega = 7 \quad \Rightarrow \quad \text{exactly 7 customers arrived in the hour}$$

### Random Variable X(ω)
$$X(\omega) = \text{number of events (customers) in the fixed interval}$$

For the example above: $X(\omega) = 7$

---

## 2. PMF and Parameter

### Probability Mass Function (PMF)
$$\boxed{P(X = k) = \frac{e^{-\lambda} \cdot \lambda^k}{k!}}, \quad k = 0, 1, 2, 3, \ldots$$

### The Parameter λ (lambda)

| Symbol | Name | Meaning |
|--------|------|---------|
| λ | rate parameter | **average number of events** in the interval |
| λ > 0 | always positive | must be a positive real number |

**Examples of λ:**
- λ = 2 → on average 2 customers per hour
- λ = 0.5 → on average 1 customer every 2 hours
- λ = 10 → on average 10 events per interval

### Where Does the Formula Come From?
| Part | Role |
|------|------|
| $e^{-\lambda}$ | normalizing constant (ensures probabilities sum to 1) |
| $\lambda^k$ | how likely it is to get $k$ events given average rate λ |
| $k!$ | corrects for the fact that order doesn't matter |

---

## 3. Support

$$\text{Support} = \{0, 1, 2, 3, \ldots\} = \mathbb{Z}_{\geq 0}$$

### Key Points
- **Starts at 0** — zero events is always possible (unlike Geometric which starts at 1)
- **No upper bound** — infinitely many events are theoretically possible
- **Always positive probability** — $P(X=k) > 0$ for every $k \geq 0$

> **Intuition:** You can't have −3 customers. But there's no law preventing 1,000 — it's just extremely unlikely.

---

## 4. PMF Graphs for Several Values of λ

```
P(X=k)          λ = 1
 0.37 |  *
 0.18 |     *
 0.06 |        *
 0.02 |           *  *
      +---------------------------> k
        0  1  2  3  4  5  6

P(X=k)          λ = 3
 0.22 |        *
 0.22 |     *     *
 0.15 |  *           *
 0.07 |                 *
 0.03 |                    *
      +---------------------------> k
        0  1  2  3  4  5  6  7

P(X=k)          λ = 7
 0.15 |                 *
 0.15 |              *     *
 0.11 |           *           *
 0.07 |        *                  *
 0.03 |     *                        *
 0.01 |  *
      +---------------------------> k
        0  1  2  3  4  5  6  7  8  9 10 11
```

**Key shapes:**
- λ = 1 → very right-skewed, most mass at k = 0 and 1
- λ = 3 → peak around 2–3, moderate skew
- λ = 7 → peak around 6–7, nearly symmetric (bell-shaped)

---

## 5. CDF Graphs for the Same Values of λ

$$F(k) = P(X \leq k) = \sum_{j=0}^{k} \frac{e^{-\lambda} \lambda^j}{j!}$$

```
F(k)            λ = 1
 1.0 |               * * * * *
 0.7 |         *
 0.5 |      *
 0.3 |   *
     | *
 0.0 +----------------------------> k
       0  1  2  3  4  5

F(k)            λ = 3
 1.0 |                     * * *
 0.8 |               *
 0.6 |         *
 0.4 |      *
 0.2 |   *
 0.0 +----------------------------> k
       0  1  2  3  4  5  6  7

F(k)            λ = 7
 1.0 |                           * *
 0.8 |                     *
 0.6 |               *
 0.4 |         *
 0.2 |      *
 0.0 +----------------------------> k
       0  2  4  6  8 10 12 14
```

**Key shapes:** Staircase function, each step size = PMF value at that k. Rises slowly for large λ.

---

## 6. How Shape Changes When λ Increases

| λ small (e.g. 0.5) | λ medium (e.g. 3) | λ large (e.g. 10) |
|--------------------|-------------------|--------------------|
| Most mass at k = 0 | Peak around k = λ | Peak around k = λ |
| Strongly right-skewed | Moderately skewed | Nearly symmetric |
| PMF drops quickly | PMF spreads out | PMF looks bell-shaped |
| CDF rises very fast | CDF rises moderately | CDF rises slowly |

### The Key Rule
> **As λ increases:**
> 1. The peak of the PMF **shifts right** to $k \approx \lambda$
> 2. The PMF **spreads wider** (variance = λ, so spread = √λ)
> 3. The shape becomes **more symmetric** (approaches Normal distribution)

### Mean and Variance
$$E[X] = \lambda \qquad \text{Var}(X) = \lambda$$

Both equal λ — this is a unique and memorable property.

---

## 7. Computing Probabilities

### P(X = k) — exactly k events

$$P(X = k) = \frac{e^{-\lambda} \cdot \lambda^k}{k!}$$

**Example** (λ = 3, k = 2):
$$P(X=2) = \frac{e^{-3} \cdot 3^2}{2!} = \frac{0.0498 \cdot 9}{2} = 0.2240$$

---

### P(X ≤ k) — at most k events

$$P(X \leq k) = \sum_{j=0}^{k} \frac{e^{-\lambda} \lambda^j}{j!}$$

**Example** (λ = 3, k = 2):
$$P(X \leq 2) = P(0) + P(1) + P(2) = 0.0498 + 0.1494 + 0.2240 = 0.4232$$

---

### P(X ≥ k) — at least k events

$$P(X \geq k) = 1 - P(X \leq k-1)$$

**Example** (λ = 3, k = 2):
$$P(X \geq 2) = 1 - P(X \leq 1) = 1 - (0.0498 + 0.1494) = 0.8008$$

---

### P(a ≤ X ≤ b) — events fall in a window

$$P(a \leq X \leq b) = P(X \leq b) - P(X \leq a-1) = \sum_{j=a}^{b} \frac{e^{-\lambda} \lambda^j}{j!}$$

**Example** (λ = 3, a = 2, b = 5):
$$P(2 \leq X \leq 5) = P(X \leq 5) - P(X \leq 1)$$
$$= 0.9161 - 0.1991 = 0.7170$$

---

## 8. CDF vs Direct Summation

Both methods give the **same answer** — they are mathematically identical. The CDF is just a shorthand for the sum.

### Example: P(X ≤ 3) with λ = 2

**Method 1 — Direct Summation (PMF)**

| k | Formula | Value |
|---|---------|-------|
| 0 | $e^{-2} \cdot 2^0 / 0!$ | 0.1353 |
| 1 | $e^{-2} \cdot 2^1 / 1!$ | 0.2707 |
| 2 | $e^{-2} \cdot 2^2 / 2!$ | 0.2707 |
| 3 | $e^{-2} \cdot 2^3 / 3!$ | 0.1804 |
| **Sum** | | **0.8571** |

**Method 2 — CDF Formula**
$$P(X \leq 3) = F(3) = 1 - \sum_{j=4}^{\infty} P(j)$$

Using tables or software: $F(3) = \mathbf{0.8571}$ ✅

> **When to use each:**
> - **Direct summation** — when you need to see each term, or when the range is small
> - **CDF / software** — when k is large or you want a quick answer

---

## 9. Practical Applications

| Application | Interval | λ (typical) |
|-------------|----------|-------------|
| **Call center** — calls per minute | 1 minute | 3–10 calls |
| **Web server** — requests per second | 1 second | 100–10,000 |
| **Radioactive decay** — particles per second | 1 second | depends on material |
| **Typos in a book** — errors per page | 1 page | 0.5–2 |
| **Car accidents** — accidents per week in a city | 1 week | 2–20 |
| **Emails received** — emails per hour | 1 hour | 1–50 |
| **Mutations in DNA** — mutations per replication | 1 replication | very small |
| **Earthquakes** — quakes per year in a region | 1 year | 0.1–5 |

### When Is the Poisson Model Appropriate?
Use Poisson when:
1. Events are **rare** relative to the interval
2. Events occur **independently**
3. The **rate is constant** over the interval
4. You are counting **occurrences**, not measuring size

---

## 10. Poisson in the Discrete Distribution Family

| Property | Poisson | Geometric | Binomial |
|----------|---------|-----------|----------|
| **Counts** | events in interval | trials until 1st success | successes in $n$ trials |
| **Support** | $\{0, 1, 2, \ldots\}$ | $\{1, 2, 3, \ldots\}$ | $\{0, 1, \ldots, n\}$ |
| **Parameter(s)** | λ | p | n, p |
| **Mean** | λ | 1/p | np |
| **Variance** | λ | $(1-p)/p^2$ | $np(1-p)$ |
| **Mean = Variance?** | ✅ Always | ❌ No | ❌ No |
| **Infinite support?** | ✅ Yes | ✅ Yes | ❌ No |
| **Includes 0?** | ✅ Yes | ❌ No | ✅ Yes |

### Poisson as Limit of Binomial
When $n$ is large, $p$ is small, and $np = \lambda$ stays fixed:
$$\text{Binomial}(n, p) \xrightarrow{n \to \infty,\ p \to 0} \text{Poisson}(\lambda)$$

> **Rule of thumb:** Use Poisson approximation when $n > 20$ and $p < 0.05$.

### λ Slider — How to Think About It

```
λ = 0.5   ████░░░░░░░░░░░░░  skewed right, peak at 0
λ = 1     ████████░░░░░░░░░  peak at 0–1
λ = 3     ░░████████████░░░  peak at 2–3
λ = 5     ░░░░████████████░  peak at 4–5, mild skew
λ = 10    ░░░░░░░░████████░  peak at 9–10, near-symmetric
λ = 20    ░░░░░░░░░░░░████░  very symmetric, wide spread
```

> As you slide λ from small to large, watch the peak move right and the bell widen.

---

## Quick Reference Card

$$P(X=k) = \frac{e^{-\lambda}\lambda^k}{k!} \qquad P(X \leq k) = \sum_{j=0}^{k}\frac{e^{-\lambda}\lambda^j}{j!} \qquad P(X \geq k) = 1 - P(X \leq k-1)$$

$$E[X] = \lambda \qquad \text{Var}(X) = \lambda \qquad \text{Support: } k \in \{0,1,2,\ldots\}$$

$$P(a \leq X \leq b) = P(X \leq b) - P(X \leq a-1)$$
