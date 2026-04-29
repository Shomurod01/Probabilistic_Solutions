# Task 5 — Multinomial Model (Categories of Outcomes)

---

## Task 1: Describe the Random Experiment

A fair six-sided die is rolled **5 times independently**. Each result is classified into one of three equally likely categories:

| Category | Outcomes | Probability |
|----------|----------|-------------|
| Small | 1 or 2 | $p_1 = \frac{1}{3}$ |
| Medium | 3 or 4 | $p_2 = \frac{1}{3}$ |
| Large | 5 or 6 | $p_3 = \frac{1}{3}$ |

Each probability equals $\frac{1}{3}$ because two faces out of six fall into each category:

$$P(\text{small}) = \frac{2}{6} = \frac{1}{3}, \quad P(\text{medium}) = \frac{2}{6} = \frac{1}{3}, \quad P(\text{large}) = \frac{2}{6} = \frac{1}{3}$$

The categories are **mutually exclusive** (a roll belongs to exactly one) and **collectively exhaustive** (every roll belongs to some category).

---

## Task 2: Define the Sample Space

Each outcome is a triple $(x_1, x_2, x_3)$ where $x_i$ counts how many rolls fell into category $i$.

$$\Omega = \{(x_1, x_2, x_3) \mid x_1 + x_2 + x_3 = 5, \quad x_i \in \mathbb{N}_0\}$$

The total number of outcomes (by stars and bars):

$$|\Omega| = \binom{5 + 3 - 1}{3 - 1} = \binom{7}{2} = 21$$

**Selected examples:**

| $(x_1, x_2, x_3)$ | Meaning |
|--------------------|---------|
| $(5, 0, 0)$ | All 5 rolls were small |
| $(2, 2, 1)$ | 2 small, 2 medium, 1 large |
| $(0, 0, 5)$ | All 5 rolls were large |

---

## Task 3: Specify the Multinomial Distribution

The probability of observing exactly $x_1$ small, $x_2$ medium, $x_3$ large results is:

$$\boxed{P(X_1 = x_1, X_2 = x_2, X_3 = x_3) = \frac{5!}{x_1!\, x_2!\, x_3!} \cdot \left(\frac{1}{3}\right)^5}$$

**Worked example** — probability of $(x_1=2, x_2=2, x_3=1)$:

$$P = \frac{5!}{2!\cdot 2!\cdot 1!} \cdot \left(\frac{1}{3}\right)^5 = 30 \cdot \frac{1}{243} = \frac{30}{243} \approx 12.35\%$$

**Edge case** — all 5 rolls small $(x_1=5, x_2=0, x_3=0)$:

$$P = \frac{5!}{5!\cdot 0!\cdot 0!} \cdot \left(\frac{1}{3}\right)^5 = 1 \cdot \frac{1}{243} \approx 0.41\%$$

---

## Task 4: Interpret the Parameters

| Parameter | Value | Interpretation |
|-----------|-------|----------------|
| $n = 5$ | 5 rolls | Fixed number of trials; enforces $x_1 + x_2 + x_3 = 5$ |
| $p_1 = p_2 = p_3 = \frac{1}{3}$ | Equal probabilities | No category is favoured; all outcomes are equally likely per roll |
| $\frac{n!}{x_1!\, x_2!\, x_3!}$ | Varies | Counts distinct orderings that produce the same counts |
| $p_1 + p_2 + p_3 = 1$ | Constraint | Categories cover all possible outcomes |

**The multinomial coefficient explained simply:** for $(2, 2, 1)$ the coefficient is 30 — meaning
there are **30 different sequences** of 5 rolls that all produce the same final counts.
Each sequence has probability $\left(\frac{1}{3}\right)^5$, so the total is $30 \times \frac{1}{243}$.
