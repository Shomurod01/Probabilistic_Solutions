# 📘 Task 2 — Rolling a Die

## 🔹 Useful Definitions and Formulas

### 1. Sample Space
The sample space is the set of all possible elementary outcomes of a random experiment:

$$
\Omega = \{\omega_1, \omega_2, \dots, \omega_n\}
$$

---

### 2. Elementary Outcome
An elementary outcome is a **single complete result** of the experiment.

---

### 3. Number of Outcomes for Die Rolls

If a fair six-sided die is rolled \( n \) times, then the number of possible outcomes is:

$$
|\Omega_n| = 6^n
$$

Each roll has 6 possible results (1 to 6), and outcomes are ordered.

---

## ✅ Problem Solution

### 🔹 Given:

- A fair six-sided die is rolled  
- Possible outcomes: \( \{1,2,3,4,5,6\} \)  
- The **order of outcomes matters**

---

## 1️⃣ Sample Space for One Roll \( \Omega_1 \)

Possible outcomes:

$$
1,2,3,4,5,6
$$

$$
\Omega_1 = \{1,2,3,4,5,6\}
$$

### Number of outcomes:

$$
|\Omega_1| = 6
$$

### Interpretation:

Each elementary outcome represents the result of **one die roll**:
- \(1\): die shows 1  
- \(6\): die shows 6  

---

## 2️⃣ Sample Space for Two Rolls \( \Omega_2 \)

All ordered pairs:

$$
(1,1),(1,2),(1,3),(1,4),(1,5),(1,6),
(2,1),(2,2),(2,3),(2,4),(2,5),(2,6),
(3,1),(3,2),(3,3),(3,4),(3,5),(3,6),
(4,1),(4,2),(4,3),(4,4),(4,5),(4,6),
(5,1),(5,2),(5,3),(5,4),(5,5),(5,6),
(6,1),(6,2),(6,3),(6,4),(6,5),(6,6)
$$

$$
\Omega_2 = \{(i,j) : i,j \in \{1,2,3,4,5,6\}\}
$$

### Number of outcomes:

$$
|\Omega_2| = 36 = 6^2
$$

### Interpretation:

Each elementary outcome represents the result of **two ordered die rolls**:
- \((2,5)\): first roll is 2, second roll is 5  
- \((6,1)\): first roll is 6, second roll is 1  

---

## 3️⃣ Sample Space for Three Rolls \( \Omega_3 \)

All ordered triples:

$$
(i,j,k) \text{ where } i,j,k \in \{1,2,3,4,5,6\}
$$

$$
\Omega_3 = \{(i,j,k) : i,j,k \in \{1,2,3,4,5,6\}\}
$$

### Number of outcomes:

$$
|\Omega_3| = 216 = 6^3
$$

### Interpretation:

Each elementary outcome represents the result of **three ordered die rolls**:
- \((1,3,6)\): first roll 1, second 3, third 6  
- \((5,5,2)\): first roll 5, second 5, third 2  

---

## 📌 Final Answers

$$
\Omega_1 = \{1,2,3,4,5,6\}, \quad |\Omega_1| = 6
$$

$$
\Omega_2 = \{(i,j) : i,j \in \{1,2,3,4,5,6\}\}, \quad |\Omega_2| = 36
$$

$$
\Omega_3 = \{(i,j,k) : i,j,k \in \{1,2,3,4,5,6\}\}, \quad |\Omega_3| = 216
$$

---

## 🔹 Key Insight

$$
|\Omega_n| = 6^n
$$

Each elementary outcome is an **ordered sequence of \( n \) die roll results**.
