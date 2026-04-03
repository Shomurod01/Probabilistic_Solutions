# Task 5 — Combinations

## Useful Definitions and Formulas

### 1. Combination
The number of ways to choose \( k \) elements from \( n \) distinct elements without regard to order:

$$
C(n, k) = \binom{n}{k} = \frac{n!}{k!(n - k)!}
$$

---

### 2. Complement Principle
To count selections with at least one condition:
- Sometimes it is easier to compute the total and subtract the undesired cases.

$$
\text{At least one} = \text{Total} - \text{None}
$$

---

### 3. Fixed Element Method
If a particular element must be included:
- Fix that element,
- Choose the remaining \( k - 1 \) elements from the remaining pool.

---

# Solutions

## 1. A committee of 4 people is chosen from 12 students. How many committees are possible?

Order does not matter, so we use combinations:

$$
\binom{12}{4} = \frac{12!}{4! \cdot 8!}
$$

Compute:

$$
\binom{12}{4} = \frac{12 \cdot 11 \cdot 10 \cdot 9}{4 \cdot 3 \cdot 2 \cdot 1} = 495
$$

**Answer:** 495 committees

---

## 2. How many committees contain a particular student?

Fix the particular student, then choose the remaining 3 members from the other 11 students:

$$
\binom{11}{3}
$$

Compute:

$$
\binom{11}{3} = \frac{11 \cdot 10 \cdot 9}{3 \cdot 2 \cdot 1} = 165
$$

**Answer:** 165 committees

---

## 3. How many committees contain at least one of two particular students?

Use the complement principle.

- Total committees:

$$
\binom{12}{4} = 495
$$

- Committees containing none of the two particular students:
  - Choose all 4 from the remaining 10 students:

$$
\binom{10}{4}
$$

Compute:

$$
\binom{10}{4} = \frac{10 \cdot 9 \cdot 8 \cdot 7}{4 \cdot 3 \cdot 2 \cdot 1} = 210
$$

Now subtract:

$$
495 - 210 = 285
$$

**Answer:** 285 committees

---

## 4. How many committees contain exactly two women if the group consists of 7 men and 5 women?

We need:
- Exactly 2 women from 5 women
- Exactly 2 men from 7 men

Number of ways:

Choose women:

$$
\binom{5}{2}
$$

Choose men:

$$
\binom{7}{2}
$$

Multiply:

$$
\binom{5}{2} \cdot \binom{7}{2}
$$

Compute:

$$
\binom{5}{2} = 10, \quad \binom{7}{2} = 21
$$

$$
10 \cdot 21 = 210
$$

**Answer:** 210 committees
