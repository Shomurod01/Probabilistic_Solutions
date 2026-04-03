# Task 11 — Modeling Outcomes

## Key Idea

In combinatorics and probability, the number of possible outcomes depends not only on the experiment itself, but also on **how the outcomes are represented (modeled)**.

The same physical experiment can lead to different counting results depending on the assumptions used in modeling.

---

## 1. Distinguishable vs. Indistinguishable Objects

### Distinguishable Objects
Objects are considered unique (e.g., different people, labeled balls).

- Swapping two objects produces a different outcome.
- Counting typically uses permutations or combinations.

### Indistinguishable Objects
Objects are identical (e.g., identical balls of the same color).

- Swapping them does not produce a new outcome.
- Counting is reduced since duplicates are not considered distinct.

---

## 2. Order Recorded vs. Order Ignored

### Order Recorded
- Outcomes that differ in sequence are considered different.
- Example: (A, B, C) ≠ (B, A, C)

Used in:
- Permutations
- k-permutations
- Sequences

### Order Ignored
- Only the selected set matters, not the arrangement.
- Example: {A, B, C} is the same regardless of order.

Used in:
- Combinations

---

## 3. Positions Treated as Distinct Places

When positions are distinct (e.g., seats in a row, slots in a code):

- Each position is labeled (1st, 2nd, 3rd, etc.).
- Assignments depend on which object goes into which position.
- Order becomes inherently important.

Examples:
- Seating arrangements
- PIN codes
- Ranking problems

---

## 4. Same Experiment, Different Models

A single experiment can be modeled differently:

### Example: Drawing 3 balls from an urn

#### Model A — Order Ignored
- Only the set of balls matters.
- Use combinations:
  
$$
\binom{n}{k}
$$

#### Model B — Order Recorded
- The sequence of draws matters.
- Use permutations:

$$
P(n, k)
$$

#### Model C — Recording Colors Only
- Outcomes are based on categories (e.g., R, B, G).
- Model as sequences with repetition:

$$
\text{number of outcomes} = c^k
$$

where \( c \) is the number of categories and \( k \) is the number of draws.

---

## 5. Summary

The number of possible outcomes depends on:

- Whether objects are distinguishable or identical  
- Whether order matters  
- Whether positions are labeled and distinct  

Careful identification of these assumptions is essential before choosing the appropriate counting model (permutation, combination, sequence, etc.).

---
