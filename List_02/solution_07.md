# Task 7: k-Permutations (Ordered Selections Without Repetition)

## 1. Concept Overview
A **k-permutation** is an ordered selection of $k$ elements from a set of $n$ elements, where no element is repeated. 

### Key Characteristics:
* **Selection:** Only some objects are chosen ($k$ out of $n$).
* **Order:** The sequence matters (e.g., 1-2-3 is different from 3-2-1).
* **No Repetition:** Once an object is picked, it cannot be used again.

### The Formula:
The number of ways to arrange these elements is given by:
$$P(n, k) = \frac{n!}{(n - k)!}$$

---

## 2. The "Slot Method" Logic
Before using the formula, it is helpful to visualize "slots" being filled:
1.  **First slot:** $n$ choices available.
2.  **Second slot:** $n-1$ choices available (since one is gone).
3.  **Third slot:** $n-2$ choices available.
4.  Keep going until all $k$ slots are full.

---

## 3. Step-by-Step Solutions

### Question 1: Assigning Places Among 12 Runners
**Problem:** In how many ways can the first three places be assigned among 12 runners?

* **Step 1: Identify $n$ and $k$.**
    * Total items ($n$) = 12 runners.
    * Slots to fill ($k$) = 3 (1st, 2nd, and 3rd place).
* **Step 2: Apply the logic.**
    * 1st Place: 12 options.
    * 2nd Place: 11 options.
    * 3rd Place: 10 options.
* **Step 3: Calculation.**
    $$12 \times 11 \times 10 = 1,320$$
* **Result:** There are **1,320** ways to assign the top three places.

---

### Question 2: 4-Digit Numbers with Distinct Digits (1–9)
**Problem:** How many 4-digit numbers with distinct digits can be formed from the digits 1–9?

* **Step 1: Identify $n$ and $k$.**
    * Total digits available ($n$) = 9 (the set {1, 2, 3, 4, 5, 6, 7, 8, 9}).
    * Digits to select ($k$) = 4.
* **Step 2: Apply the formula.**
    $$P(9, 4) = \frac{9!}{(9 - 4)!} = \frac{9!}{5!}$$
* **Step 3: Expand and simplify.**
    $$9 \times 8 \times 7 \times 6 = 3,024$$
* **Result:** There are **3,024** possible 4-digit numbers.

---

### Question 3: Numbers Divisible by 5
**Problem:** How many of the numbers from Question 2 are divisible by 5?

* **Step 1: Identify the Constraint.**
    For a number to be divisible by 5, it must end in 0 or 5. Since our set is 1–9, the **last digit must be 5**.
* **Step 2: Fill the restricted slot first.**
    * **Last Digit:** Only **1** choice (the digit 5).
* **Step 3: Fill the remaining slots.**
    We now have 3 empty slots left and 8 remaining digits to choose from (since 5 is already used).
    * 1st Digit: 8 choices.
    * 2nd Digit: 7 choices.
    * 3rd Digit: 6 choices.
* **Step 4: Calculation.**
    $$(8 \times 7 \times 6) \times 1 = 336$$
* **Result:** There are **336** numbers divisible by 5.

---

## 4. Summary Table

| Scenario | Total (n) | Selection (k) | Logic | Total Ways |
| :--- | :---: | :---: | :--- | :--- |
| **Runners** | 12 | 3 | $12 \times 11 \times 10$ | 1,320 |
| **4-Digit Numbers** | 9 | 4 | $9 \times 8 \times 7 \times 6$ | 3,024 |
| **Divisible by 5** | 8* | 3* | $(8 \times 7 \times 6) \times 1$ | 336 |
