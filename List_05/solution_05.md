# Poisson Distribution 

---

## 0. The Experiment

**Idea:** Count how many random events happen in a fixed interval of time or space.

**Real example:** You sit at a coffee shop for **1 hour** and count how many customers walk in.

**Rules for this experiment:**
- Events happen **randomly** (you cannot predict exactly when)
- Events happen **independently** (one customer arriving does not affect the next)
- The **average rate is constant** (same average every hour)

### Sample Space Ω

All possible counts you could observe:

$$\Omega = \{0, 1, 2, 3, 4, \ldots\}$$

Zero customers is possible. There is no maximum — in theory, any count can happen.

### One Elementary Outcome ω

$$\omega = 7$$

This means: **exactly 7 customers arrived during that 1 hour.**

> Why 7? It is just one example we chose. It could have been 0, 3, or 20. We pick a concrete number so the idea is easy to follow.

### Random Variable X(ω)

$$X(\omega) = \text{number of customers (events) counted in the interval}$$

So for our example: $X(\omega) = 7$

---

## 1. The PMF and Its Parameter

### The Parameter λ (lambda)

λ is the **average number of events per interval**.

You get λ from **real data**, not from a formula:

$$\lambda = \frac{\text{total events observed}}{\text{total intervals observed}}$$

**Example:** 200 customers arrived over 100 hours → $\lambda = 200 \div 100 = 2$

| λ value | Plain meaning |
|---------|--------------|
| λ = 0.5 | on average 1 event every 2 hours |
| λ = 2   | on average 2 events per hour |
| λ = 10  | on average 10 events per hour (busy!) |

> λ is always **positive**. You measure it from the real world, then plug it into the formula.

### Probability Mass Function (PMF)

$$\boxed{P(X = k) = \frac{e^{-\lambda} \cdot \lambda^k}{k!}}$$

where $k = 0, 1, 2, 3, \ldots$

**What each piece means:**

| Piece | What it does |
|-------|-------------|
| $e^{-\lambda}$ | makes all probabilities sum to exactly 1 |
| $\lambda^k$ | captures how likely k events are given the average rate |
| $k!$ | corrects for counting (order does not matter) |

**Worked example** — λ = 3, find P(X = 2):

$$P(X = 2) = \frac{e^{-3} \cdot 3^2}{2!} = \frac{0.0498 \times 9}{2} = 0.2240$$

> There is a **22.4% chance** that exactly 2 customers arrive.

---

## 2. Support

$$\text{Support} = \{0, 1, 2, 3, \ldots\}$$

**Two key points:**

**Starts at 0** — zero events is always possible. (This is different from the Geometric distribution which starts at 1.)

**No upper limit** — for any number k you name, $P(X = k) > 0$, so the support cannot stop at any finite value.

> Imagine the coffee shop on an unusually crazy day — 100 customers in one hour is extremely unlikely but not impossible.

---

## 3. PMF Graphs — What They Show

Each graph answers: **given λ, how likely is each count k?**

- **Horizontal axis** = k (number of events: 0, 1, 2, 3, ...)
- **Vertical axis** = P(X = k) (probability of that exact count)
- **Each bar** = one possible outcome and its probability

### λ = 1

```
P(X=k)
 0.37 | **
 0.18 |    **
 0.06 |       **
 0.02 |          ** **
      +----------------------> k
        0  1  2  3  4  5
```

Peak is at k = 0 and k = 1. Getting k = 4 or more is very unlikely.

**Plain meaning:** When the average is 1 customer per hour, seeing 0 or 1 customer is the most common outcome.

### λ = 3

```
P(X=k)
 0.22 |       ** **
 0.15 |    **          **
 0.07 |                   **
 0.02 |                      ** **
      +----------------------> k
        0  1  2  3  4  5  6  7
```

Peak is around k = 2 and k = 3. The graph spreads wider.

**Plain meaning:** When the average is 3, the most common outcomes cluster around 2–4.

### λ = 7

```
P(X=k)
 0.15 |             ** **
 0.11 |          **       **
 0.07 |       **              **
 0.03 |    **                    **
 0.01 | **
      +-----------------------------> k
        0  1  2  3  4  5  6  7  8  9 10 11
```

Peak is around k = 6 and k = 7. The graph looks almost like a bell curve.

**Plain meaning:** When the average is 7, k = 0 is nearly impossible. The distribution is wide and symmetric.

### Summary of Graph Shapes

| λ | Peak at | Shape |
|---|---------|-------|
| 1 | k = 0–1 | Strongly skewed right |
| 3 | k = 2–3 | Moderate spread |
| 7 | k = 6–7 | Wide, nearly symmetric |

> **Key rule:** The peak always sits near k = λ. As λ grows, the graph shifts right and becomes wider and more symmetric.

---

## 4. CDF Graphs

The CDF answers: **what is the probability of getting k or fewer events?**

$$F(k) = P(X \leq k) = \sum_{j=0}^{k} \frac{e^{-\lambda} \lambda^j}{j!}$$

### λ = 1

```
F(k)
 1.0 |            * * * *
 0.7 |       *
 0.5 |    *
 0.3 | *
     +----------------------> k
       0  1  2  3  4  5
```

Reaches near 1.0 quickly (by k = 3).

### λ = 3

```
F(k)
 1.0 |                  * * *
 0.8 |            *
 0.6 |       *
 0.4 |    *
 0.2 | *
     +----------------------> k
       0  1  2  3  4  5  6
```

Climbs more slowly, reaches near 1.0 by k = 7.

### λ = 7

```
F(k)
 1.0 |                        * *
 0.8 |                  *
 0.6 |            *
 0.4 |       *
 0.2 |    *
 0.0 | *
     +-----------------------------> k
       0  2  4  6  8  10  12
```

Climbs slowly, needs k ≈ 12 to approach 1.0.

### Summary of CDF Shapes

| λ | Rises... | Reaches ~1.0 by... |
|---|----------|---------------------|
| 1 | Very fast | k = 3–4 |
| 3 | Medium | k = 7–8 |
| 7 | Slowly | k = 12–14 |

---

## 5. How Shape Changes When λ Increases

Think of sliding λ like a volume knob:

```
λ = 0.5  →  peak at k=0,  very short and skewed
λ = 1    →  peak at k=0-1, still skewed
λ = 3    →  peak at k=2-3, spreading out
λ = 5    →  peak at k=4-5, mild skew
λ = 10   →  peak at k=9-10, nearly symmetric bell
λ = 20   →  peak at k=19-20, very wide and symmetric
```

**Three things that always happen as λ grows:**

1. The peak **moves right** (toward higher k values)
2. The graph **gets wider** (more spread, variance = λ)
3. The shape **becomes more symmetric** (less skewed)

---

## 6. Computing Probabilities

All four types use the same base formula. We use **λ = 3** for all examples.

---

### P(X = k) — exactly k events

$$P(X = k) = \frac{e^{-\lambda} \lambda^k}{k!}$$

**Example:** What is the probability of exactly 2 customers?

$$P(X = 2) = \frac{e^{-3} \cdot 9}{2} = 0.2240$$

---

### P(X ≤ k) — at most k events

$$P(X \leq k) = \sum_{j=0}^{k} P(X = j)$$

**Example:** What is the probability of 2 or fewer customers?

$$P(X \leq 2) = P(0) + P(1) + P(2) = 0.0498 + 0.1494 + 0.2240 = 0.4232$$

---

### P(X ≥ k) — at least k events

$$P(X \geq k) = 1 - P(X \leq k-1)$$

**Example:** What is the probability of 2 or more customers?

$$P(X \geq 2) = 1 - P(X \leq 1) = 1 - (0.0498 + 0.1494) = 0.8008$$

---

### P(a ≤ X ≤ b) — count falls in a range

$$P(a \leq X \leq b) = P(X \leq b) - P(X \leq a-1)$$

**Example:** What is the probability of between 2 and 5 customers?

$$P(2 \leq X \leq 5) = P(X \leq 5) - P(X \leq 1) = 0.9161 - 0.1991 = 0.7170$$

---

### Quick Reference Table (λ = 3)

| k | P(X=k) | P(X≤k) | P(X≥k) |
|---|--------|--------|--------|
| 0 | 0.0498 | 0.0498 | 1.0000 |
| 1 | 0.1494 | 0.1991 | 0.9502 |
| 2 | 0.2240 | 0.4232 | 0.8009 |
| 3 | 0.2240 | 0.6472 | 0.5768 |
| 4 | 0.1680 | 0.8153 | 0.3528 |
| 5 | 0.1008 | 0.9161 | 0.1847 |

---

## 7. CDF vs Direct Summation

Both methods give the **same answer**. The CDF is just a shortcut name for the sum.

### Example: P(X ≤ 3) with λ = 2

**Method 1 — Add up each term one by one:**

| k | Calculation | Result |
|---|-------------|--------|
| 0 | $e^{-2} \cdot 1 / 1$ | 0.1353 |
| 1 | $e^{-2} \cdot 2 / 1$ | 0.2707 |
| 2 | $e^{-2} \cdot 4 / 2$ | 0.2707 |
| 3 | $e^{-2} \cdot 8 / 6$ | 0.1804 |
| **Total** | | **0.8571** |

**Method 2 — Use the CDF directly:**

$$F(3) = P(X \leq 3) = 0.8571 \checkmark$$

Same answer. ✅

| When to use | Method |
|-------------|--------|
| You want to see each step clearly | Direct summation |
| You want a fast answer | CDF (table or software) |
| k is a large number | CDF (summing 50 terms by hand is painful) |

---

## 8. Practical Applications

| Field | What X counts | Typical λ |
|-------|--------------|-----------|
| Call center | calls per minute | 3–10 |
| Web server | requests per second | 100–10,000 |
| Radioactive decay | particles per second | depends on material |
| Book editing | typos per page | 0.5–2 |
| Road safety | accidents per week | 2–20 |
| Email inbox | emails per hour | 1–50 |
| Medicine | mutations per cell division | very small |
| Geology | earthquakes per year in a region | 0.1–5 |

**When is the Poisson model the right choice?**

Ask yourself four questions:

1. Am I **counting** occurrences? (not measuring size or time)
2. Are events **independent**?
3. Is the rate **constant** over the interval?
4. Are events **rare** compared to the interval length?

If yes to all four → use Poisson.

---

## 9. Poisson in the Distribution Family

| Property | Poisson | Geometric | Binomial |
|----------|---------|-----------|----------|
| Counts | events in interval | trials until 1st success | successes in n trials |
| Support | {0, 1, 2, ...} | {1, 2, 3, ...} | {0, 1, ..., n} |
| Parameter | λ | p | n, p |
| Mean | λ | 1/p | np |
| Variance | λ | (1−p)/p² | np(1−p) |
| Mean = Variance | ✅ always | ❌ no | ❌ no |
| Infinite support | ✅ yes | ✅ yes | ❌ no |
| Includes 0 | ✅ yes | ❌ no | ✅ yes |

### Special Fact: Poisson as a Limit of Binomial

When trials n is very large and probability p is very small, and their product stays fixed:

$$np = \lambda \quad \Rightarrow \quad \text{Binomial}(n, p) \approx \text{Poisson}(\lambda)$$

**Rule of thumb:** Use the Poisson approximation when $n > 20$ and $p < 0.05$.

---

## Quick Reference Card

$$P(X=k) = \frac{e^{-\lambda}\lambda^k}{k!}$$

$$P(X \leq k) = \sum_{j=0}^{k}\frac{e^{-\lambda}\lambda^j}{j!} \qquad P(X \geq k) = 1 - P(X \leq k-1)$$

$$P(a \leq X \leq b) = P(X \leq b) - P(X \leq a-1)$$

$$E[X] = \lambda \qquad \text{Var}(X) = \lambda \qquad \text{Support: } \{0, 1, 2, \ldots\}$$
