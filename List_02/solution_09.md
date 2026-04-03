# Task 9 — Digit Restrictions

## Useful Definitions and Formulas

### 1. Counting n-digit Numbers
A 5-digit number cannot start with 0.

- First digit: 1–9 (9 choices)
- Remaining digits: 0–9 (10 choices each)

---

### 2. Even Numbers
A number is even if its last digit is one of:
$$
\{0, 2, 4, 6, 8\}
$$

---

### 3. No Repeated Digits
Use permutations without repetition:

$$
P(n, k) = \frac{n!}{(n - k)!}
$$

---

### 4. Complement Principle
To count numbers with at least one repeated digit:

$$
\text{At least one repetition} = \text{Total} - \text{All distinct}
$$

---

# Solutions

## 1. How many 5-digit numbers exist?

- First digit: 1–9 → 9 choices  
- Remaining 4 digits: 0–9 → 10 choices each  

Total:

$$
9 \cdot 10^4 = 90000
$$

**Answer:** 90000

---

## 2. How many of them are even?

We count even 5-digit numbers.

### Case 1: Last digit is 0
- First digit: 1–9 → 9 choices  
- Middle 3 digits: 0–9 → \(10^3\)

$$
9 \cdot 10^3 = 9000
$$

### Case 2: Last digit is 2, 4, 6, or 8 (4 choices)
- First digit: 1–9 (but cannot be 0 or equal to last digit) → still 9 choices  
- Middle 3 digits: \(10^3\)

$$
4 \cdot 9 \cdot 10^3 = 36000
$$

### Total:

$$
9000 + 36000 = 45000
$$

**Answer:** 45000

---

## 3. How many contain no repeated digits?

- First digit: 1–9 → 9 choices  
- Second digit: 0–9 except the first → 9 choices  
- Third digit: 8 choices  
- Fourth digit: 7 choices  
- Fifth digit: 6 choices  

Total:

$$
9 \cdot 9 \cdot 8 \cdot 7 \cdot 6 = 27216
$$

**Answer:** 27216

---

## 4. How many contain at least one repeated digit?

Use the complement principle:

- Total 5-digit numbers:

$$
90000
$$

- Numbers with all digits distinct:

$$
27216
$$

Subtract:

$$
90000 - 27216 = 62784
$$

**Answer:** 62784
