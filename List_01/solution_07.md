# 📘 Task 7 — Events and Probabilities in Die Rolling

## 🔹 Useful Definitions and Formulas

### 1. Probability of an Event (Equally Likely Outcomes)

$$
P(A) = \frac{|A|}{|\Omega|}
$$

---

### 2. Sample Space Size for Die Rolls

$$
|\Omega_n| = 6^n
$$

---

### 3. Complement Rule

$$
P(A^c) = 1 - P(A)
$$

---

## ✅ Problem Solution

### 🔹 Given:

- A fair six-sided die  
- Outcomes: \( \{1,2,3,4,5,6\} \)  
- All elementary outcomes are **equally likely**

---

# 1️⃣ Assigning Probabilities

## 🔸 One Roll \( \Omega_1 \)

$$
\Omega_1 = \{1,2,3,4,5,6\}, \quad |\Omega_1| = 6
$$

Each outcome:

$$
P(\omega) = \frac{1}{6}
$$

---

## 🔸 Two Rolls \( \Omega_2 \)

$$
|\Omega_2| = 36
$$

Each outcome:

$$
P(\omega) = \frac{1}{36}
$$

---

## 🔸 Three Rolls \( \Omega_3 \)

$$
|\Omega_3| = 216
$$

Each outcome:

$$
P(\omega) = \frac{1}{216}
$$

---

# 2️⃣ One Die Roll

## 🔸 Event \( A_1 \): result is even

$$
A_1 = \{2,4,6\}
$$

$$
P(A_1) = \frac{3}{6} = \frac{1}{2}
$$

---

## 🔸 Event \( B_1 \): result > 4

$$
B_1 = \{5,6\}
$$

$$
P(B_1) = \frac{2}{6} = \frac{1}{3}
$$

---

## 🔸 Event \( C_1 \): result ≤ 3

$$
C_1 = \{1,2,3\}
$$

$$
P(C_1) = \frac{3}{6} = \frac{1}{2}
$$

---

# 3️⃣ Two Die Rolls

## 🔸 Event \( A_2 \): sum = 7

Possible outcomes:

$$
(1,6),(2,5),(3,4),(4,3),(5,2),(6,1)
$$

$$
P(A_2) = \frac{6}{36} = \frac{1}{6}
$$

---

## 🔸 Event \( B_2 \): same results

$$
(1,1),(2,2),(3,3),(4,4),(5,5),(6,6)
$$

$$
P(B_2) = \frac{6}{36} = \frac{1}{6}
$$

---

## 🔸 Event \( C_2 \): sum ≥ 10

Possible sums: 10, 11, 12

Outcomes:

$$
(4,6),(5,5),(6,4),(5,6),(6,5),(6,6)
$$

$$
P(C_2) = \frac{6}{36} = \frac{1}{6}
$$

---

# 4️⃣ Three Die Rolls

## 🔸 Event \( A_3 \): sum = 10

Number of solutions to:

$$
x_1 + x_2 + x_3 = 10, \quad x_i \in \{1,\dots,6\}
$$

Valid outcomes count:

$$
|A_3| = 27
$$

$$
P(A_3) = \frac{27}{216} = \frac{1}{8}
$$

---

## 🔸 Event \( B_3 \): exactly two equal

Choose:
- value for the pair: 6 ways  
- position of the different number: 3 ways  
- value of the different number: 5 ways  

$$
|B_3| = 6 \cdot 3 \cdot 5 = 90
$$

$$
P(B_3) = \frac{90}{216} = \frac{5}{12}
$$

---

## 🔸 Event \( C_3 \): two 2s and one 3

Permutations of \((2,2,3)\):

$$
|C_3| = 3
$$

$$
P(C_3) = \frac{3}{216} = \frac{1}{72}
$$

---

# 📌 Final Answers

## One Roll

$$
P(A_1) = \frac{1}{2}, \quad P(B_1) = \frac{1}{3}, \quad P(C_1) = \frac{1}{2}
$$

---

## Two Rolls

$$
P(A_2) = \frac{1}{6}, \quad P(B_2) = \frac{1}{6}, \quad P(C_2) = \frac{1}{6}
$$

---

## Three Rolls

$$
P(A_3) = \frac{1}{8}, \quad P(B_3) = \frac{5}{12}, \quad P(C_3) = \frac{1}{72}
$$

---

## 🔹 Key Insight

$$
P(A) = \frac{|A|}{|\Omega|}
$$

All problems reduce to **counting favorable outcomes** in a finite sample space.
