# Task 5 — Multinomial Model (Categories of Outcomes)

## Given

- A die is rolled \( n = 5 \) times.
- Each result is classified into 3 categories:
  - Small (1–2) → \( p_1 = \frac{1}{3} \)
  - Medium (3–4) → \( p_2 = \frac{1}{3} \)
  - Large (5–6) → \( p_3 = \frac{1}{3} \)

---

## 1. Description of the Random Experiment

We roll a fair six-sided die 5 times.

Each roll is grouped into one of three categories:
- Small (1 or 2)
- Medium (3 or 4)
- Large (5 or 6)

The result of the experiment is the number of times each category appears.

---

## 2. Sample Space \( \Omega \)

We describe outcomes using counts of categories instead of listing all sequences.

$$
\Omega = \{ (x_1, x_2, x_3) \mid x_1 + x_2 + x_3 = 5,\ x_i \ge 0 \}
$$

where:
- \( x_1 \): number of small outcomes  
- \( x_2 \): number of medium outcomes  
- \( x_3 \): number of large outcomes  

---

## 3. Multinomial Distribution

Let:
- \( X_1 \): number of small outcomes  
- \( X_2 \): number of medium outcomes  
- \( X_3 \): number of large outcomes  

Then:

$$
(X_1, X_2, X_3) \sim \text{Multinomial}(5, \tfrac{1}{3}, \tfrac{1}{3}, \tfrac{1}{3})
$$

Probability formula:

$$
P(X_1 = x_1, X_2 = x_2, X_3 = x_3)
= \frac{5!}{x_1! \, x_2! \, x_3!} \left(\frac{1}{3}\right)^5
$$

subject to:

$$
x_1 + x_2 + x_3 = 5
$$

---

## 4. Interpretation of Parameters

- \( n = 5 \): number of trials (dice rolls)
- \( k = 3 \): number of categories
- \( p_1 = p_2 = p_3 = \frac{1}{3} \): probability of each category

### Meaning:

- Each roll has an equal chance to be small, medium, or large.
- The model describes how the 5 rolls are distributed among the 3 categories.
- Example outcome:
  - \( (2, 1, 2) \) means:
    - 2 small
    - 1 medium
    - 2 large

---

## Summary

- We group outcomes into 3 categories instead of tracking exact values.
- The sample space contains all triples that sum to 5.
- The multinomial distribution gives probabilities of each possible combination.
- Since all probabilities are equal, the formula simplifies using \( (\frac{1}{3})^5 \).
