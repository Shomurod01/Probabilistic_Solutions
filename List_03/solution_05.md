# Task 5 — Multinomial Model (Categories of Outcomes)

## Useful Definitions and Formulas

### 1. Multinomial Distribution
The multinomial distribution generalizes the binomial distribution to more than two categories.

If:
- An experiment has \( n \) independent trials,
- Each trial results in one of \( k \) categories,
- Each category has fixed probability \( p_1, p_2, \dots, p_k \),

then the probability of observing counts \( x_1, x_2, \dots, x_k \) is:

$$
P(X_1 = x_1, \dots, X_k = x_k) = \frac{n!}{x_1! \cdot x_2! \cdots x_k!} \cdot p_1^{x_1} \cdot p_2^{x_2} \cdots p_k^{x_k}
$$

subject to:

$$
x_1 + x_2 + \cdots + x_k = n
$$

---

### 2. Categories of Outcomes
Instead of tracking exact outcomes, results are grouped into categories, and we count how many outcomes fall into each category.

---

# Given

- A die is rolled \( n = 5 \) times.
- Each outcome is classified into one of three categories:
  - Small: (1–2), probability \( \frac{1}{3} \)
  - Medium: (3–4), probability \( \frac{1}{3} \)
  - Large: (5–6), probability \( \frac{1}{3} \)

---

# Solutions

## 1. Describe the random experiment

The experiment consists of:
- Rolling a fair six-sided die 5 times independently,
- Each roll is classified into one of three categories:
  - Small (1 or 2)
  - Medium (3 or 4)
  - Large (5 or 6)
- The outcome of the experiment is recorded as the number of times each category occurs across the 5 rolls.

---

## 2. Define the sample space

Instead of listing all sequences of 5 rolls, the sample space is defined in terms of category counts:

$$
\Omega = \{ (x_1, x_2, x_3) \mid x_1 + x_2 + x_3 = 5,\ x_i \in \mathbb{Z}_{\ge 0} \}
$$

where:
- \( x_1 \) = number of small outcomes,
- \( x_2 \) = number of medium outcomes,
- \( x_3 \) = number of large outcomes.

---

## 3. Specify the multinomial distribution

Let:
- \( X_1 \) = number of small outcomes,
- \( X_2 \) = number of medium outcomes,
- \( X_3 \) = number of large outcomes.

Then:

$$
(X_1, X_2, X_3) \sim \text{Multinomial}(n = 5, p_1 = \tfrac{1}{3}, p_2 = \tfrac{1}{3}, p_3 = \tfrac{1}{3})
$$

The probability mass function is:

$$
P(X_1 = x_1, X_2 = x_2, X_3 = x_3) = \frac{5!}{x_1! \cdot x_2! \cdot x_3!} \left(\frac{1}{3}\right)^{x_1} \left(\frac{1}{3}\right)^{x_2} \left(\frac{1}{3}\right)^{x_3}
$$

subject to:

$$
x_1 + x_2 + x_3 = 5
$$

---

## 4. Interpret the parameters

- \( n = 5 \): the number of independent trials (dice rolls).
- \( k = 3 \): the number of categories (small, medium, large).
- \( p_1 = p_2 = p_3 = \frac{1}{3} \): the probability that a single roll falls into each category.

Interpretation:
- The parameters \( p_1, p_2, p_3 \) represent the probabilities that any single die roll belongs to each category.
- The multinomial model describes how the 5 rolls are distributed across the three categories.
- Each outcome in the sample space corresponds to a particular allocation of the 5 rolls among the categories.

---
