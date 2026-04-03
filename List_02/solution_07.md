# Task 7 — k-Permutations (Ordered Selections Without Repetition)

## Useful Definitions and Formulas

### 1. k-Permutation (Ordered Selection Without Repetition)
The number of ways to select and arrange \( k \) elements from \( n \) distinct elements:

$$
P(n, k) = \frac{n!}{(n - k)!}
$$

---

### 2. Basic Counting Principle
If a process consists of multiple independent steps, the total number of outcomes is the product of the number of choices at each step.

---

# Solutions

## 1. In how many ways can the first three places be assigned among 12 runners?

We are selecting and ordering 3 runners out of 12:

$$
P(12, 3) = \frac{12!}{(12 - 3)!} = \frac{12!}{9!}
$$

Compute:

$$
12 \cdot 11 \cdot 10 = 1320
$$

**Answer:** 1320 ways

---

## 2. How many 4-digit numbers with distinct digits can be formed from the digits 1–9?

- Digits available: 1–9 (no zero)
- No repetition allowed
- Order matters (forming a number)

This is a k-permutation:

$$
P(9, 4) = \frac{9!}{(9 - 4)!} = \frac{9!}{5!}
$$

Compute:

$$
9 \cdot 8 \cdot 7 \cdot 6 = 3024
$$

**Answer:** 3024 numbers

---

## 3. How many of these numbers are divisible by 5?

A number is divisible by 5 if its last digit is 5 (since 0 is not available).

### Step 1: Fix the last digit
- Last digit must be 5 → 1 choice

### Step 2: Fill the remaining 3 positions
- Remaining digits: from {1–9} excluding 5 → 8 digits
- Choose and arrange 3 distinct digits:

$$
P(8, 3) = 8 \cdot 7 \cdot 6
$$

Compute:

$$
8 \cdot 7 \cdot 6 = 336
$$

**Answer:** 336 numbers
