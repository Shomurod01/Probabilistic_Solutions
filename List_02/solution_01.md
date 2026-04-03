# Task 1 — Recognizing Counting Models

## Useful Definitions and Formulas

### 1. Permutation
A permutation is an arrangement of all elements of a set in a specific order.

$$
P(n) = n!
$$

---

### 2. k-Permutation (Ordered Selection Without Repetition)
Selecting and arranging \( k \) elements from \( n \) distinct elements where order matters.

$$
P(n, k) = \frac{n!}{(n - k)!}
$$

---

### 3. Combination (Unordered Selection Without Repetition)
Selecting \( k \) elements from \( n \) distinct elements where order does not matter.

$$
C(n, k) = \binom{n}{k} = \frac{n!}{k!(n - k)!}
$$

---

### 4. Permutation with Repeated Elements
Arranging elements when some are identical.

If a set has \( n \) elements with repetitions:
- \( n_1 \) identical elements of one type,
- \( n_2 \) identical elements of another type, etc.

$$
\frac{n!}{n_1! \cdot n_2! \cdots n_k!}
$$

---

### 5. Circular Permutation
Arranging \( n \) distinct objects around a circle where rotations are considered identical.

$$
(n - 1)!
$$

---

### 6. Sequence with Repetition
Forming sequences where each position can be filled independently with repetition allowed.

$$
n^k
$$

---

# Solutions

## 1. Arranging 7 students in a line

- Order matters.
- All 7 students are arranged.

**Model:** Permutation

**Explanation:**
We are arranging all elements in a linear order.

---

## 2. Choosing 4 members of a committee from 12 people

- Order does not matter.
- We are selecting a subset.

**Model:** Combination

**Explanation:**
The committee has no ordering, only membership matters.

---

## 3. Assigning gold, silver, and bronze medals among 15 athletes

- Order matters (gold, silver, bronze are distinct ranks).
- No repetition (one athlete per medal).

**Model:** k-permutation

**Explanation:**
We are selecting and ordering 3 athletes out of 15.

---

## 4. Forming a 6-digit PIN code

- Digits can repeat.
- Order matters.

**Model:** Sequence with repetition

**Explanation:**
Each of the 6 positions can be filled independently with digits (0–9), and repetition is allowed.

---

## 5. Arranging the letters of the word BANANA

- Letters include repetitions:
  - A appears 3 times
  - N appears 2 times
  - B appears 1 time

**Model:** Permutation with repeated elements

**Explanation:**
We arrange letters where some are identical.

---

## 6. Seating 6 people around a round table

- Circular arrangement.
- Rotations are considered the same.

**Model:** Circular permutation

**Explanation:**
Fix one person and arrange the remaining around them.

---
