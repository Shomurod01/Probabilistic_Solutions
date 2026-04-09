# Task 8: Sequences with Repetition

## 1. Concept Overview
A **sequence with repetition** (also known as an ordered selection with replacement) occurs when you choose $k$ elements from a set of $n$ elements, and you are allowed to pick the same element more than once.

### Key Characteristics:
* **Order matters:** In a PIN, `1-2-3` is different from `3-2-1`.
* **Repetition is allowed:** You can have a PIN like `1-1-1-1-1`.
* **Independence:** The choice for the first digit does not affect the choices for the second digit.

### The Formula:
The number of possible sequences is:
$$n^k$$
*(Where $n$ is the number of options per slot, and $k$ is the number of slots).*

---

## 2. Step-by-Step Solutions

### Question 1: How many 5-digit PIN codes are possible?
**Problem:** Digits may repeat.

* **Step 1: Identify the pool ($n$).**
    There are 10 possible digits: {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}. So, $n = 10$.
* **Step 2: Identify the slots ($k$).**
    The PIN has 5 digits. So, $k = 5$.
* **Step 3: Fill the slots.**
    * Slot 1: 10 choices
    * Slot 2: 10 choices
    * Slot 3: 10 choices
    * Slot 4: 10 choices
    * Slot 5: 10 choices
* **Step 4: Calculation.**
    $$10 \times 10 \times 10 \times 10 \times 10 = 10^5 = 100,000$$
* **Result:** There are **100,000** possible PIN codes.

---

### Question 2: How many such codes have all digits different?
**Problem:** No digits may repeat (a $k$-permutation).

* **Step 1: Fill the slots logically.**
    * Slot 1: 10 choices.
    * Slot 2: 9 choices (cannot use the digit from Slot 1).
    * Slot 3: 8 choices.
    * Slot 4: 7 choices.
    * Slot 5: 6 choices.
* **Step 2: Calculation.**
    $$10 \times 9 \times 8 \times 7 \times 6 = 30,240$$
* **Result:** There are **30,240** codes where every digit is unique.

---

### Question 3: How many codes contain at least one repeated digit?
**Problem:** This is difficult to count directly, so we use the **Complement Principle**.

* **Step 1: Understand the logic.**
    Every possible PIN code is either "all different" OR it has "at least one repeat." There is no third option. Therefore:
    $$\text{Total Codes} = (\text{All Different}) + (\text{At Least One Repeat})$$
* **Step 2: Re-arrange the formula.**
    $$\text{At Least One Repeat} = \text{Total Codes} - \text{All Different}$$
* **Step 3: Calculation.**
    Using our results from Q1 and Q2:
    $$100,000 - 30,240 = 69,760$$
* **Result:** There are **69,760** codes that contain at least one repeated digit.

---

## 3. Comparison Summary

| Scenario | Rule | Logic | Result |
| :--- | :--- | :--- | :--- |
| **Total PINs** | Repetition Allowed | $10^5$ | 100,000 |
| **All Different** | No Repetition | $P(10, 5)$ | 30,240 |
| **At Least 1 Repeat** | Complement | $Total - Unique$ | 69,760 |
