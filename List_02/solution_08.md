# Task 8 — Sequences with Repetition

## Useful Definitions and Formulas

### 1. Sequence with Repetition
When each position can be filled independently from a set of \( n \) elements and repetition is allowed:

$$
n^k
$$

where:
- \( n \) = number of available choices per position
- \( k \) = number of positions

---

### 2. Complement Principle
To count sequences with at least one repetition:

$$
\text{At least one repetition} = \text{Total} - \text{All distinct}
$$

---

### 3. Sequences with All Distinct Digits
When no repetition is allowed:

$$
P(n, k) = \frac{n!}{(n - k)!}
$$

---

# Solutions

## 1. How many 5-digit PIN codes are possible if digits may repeat?

- Each of the 5 positions can be filled with any of the 10 digits (0–9).
- Repetition is allowed.

$$
10^5 = 100000
$$

**Answer:** 100000 codes

---

## 2. How many such codes contain at least one repeated digit?

Use the complement principle:

- Total codes:

$$
10^5
$$

- Codes with all digits different:

$$
P(10, 5) = 10 \cdot 9 \cdot 8 \cdot 7 \cdot 6 = 30240
$$

Now subtract:

$$
10^5 - P(10, 5) = 100000 - 30240 = 69760
$$

**Answer:** 69760 codes

---

## 3. How many such codes have all digits different?

This is a permutation without repetition:

$$
P(10, 5) = \frac{10!}{(10 - 5)!}
$$

Compute:

$$
10 \cdot 9 \cdot 8 \cdot 7 \cdot 6 = 30240
$$

**Answer:** 30240 codes
