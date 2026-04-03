# 📘 Task 3 — Drawing Cards

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

### 3. Number of Outcomes for Card Draws

- A standard deck contains 52 distinct cards  
- The order of outcomes matters  

With replacement:

$$
|\Omega_n| = 52^n
$$

Without replacement:

$$
|\Omega_n| = 52 \cdot 51 \cdot \dots \cdot (52 - n + 1)
$$

---

## ✅ Problem Solution

### 🔹 Given:

- A standard 52-card deck  
- All cards are distinct  
- The **order of outcomes matters**

---

## 1️⃣ Sample Space for One Draw \( \Omega_1 \)

Possible outcomes:

$$
\text{All 52 individual cards}
$$

$$
\Omega_1 = \{c_1, c_2, \dots, c_{52}\}
$$

### Number of outcomes:

$$
|\Omega_1| = 52
$$

### Interpretation:

Each elementary outcome represents **one specific card drawn**:
- Example: Ace of Spades, 7 of Hearts  

---

## 2️⃣ Sample Space for Two Draws with Replacement \( \Omega_2 \)

All ordered pairs:

$$
(c_i, c_j) \text{ where } c_i, c_j \in \Omega_1
$$

$$
\Omega_2 = \{(c_i, c_j) : c_i, c_j \in \{c_1, \dots, c_{52}\}\}
$$

### Number of outcomes:

$$
|\Omega_2| = 52^2 = 2704
$$

### Interpretation:

Each elementary outcome represents **two ordered draws where the card is returned before the second draw**:
- Example: (Ace of Spades, Ace of Spades)  
- Example: (King of Hearts, 2 of Clubs)  

---

## 3️⃣ Sample Space for Two Draws without Replacement \( \Omega_2' \)

All ordered pairs of distinct cards:

$$
(c_i, c_j) \text{ where } c_i \neq c_j
$$

$$
\Omega_2' = \{(c_i, c_j) : c_i, c_j \in \{c_1, \dots, c_{52}\}, \; c_i \neq c_j\}
$$

### Number of outcomes:

$$
|\Omega_2'| = 52 \cdot 51 = 2652
$$

### Interpretation:

Each elementary outcome represents **two ordered draws without replacement**:
- Example: (Ace of Spades, King of Hearts)  
- Example: (5 of Clubs, 5 of Clubs) ❌ not allowed  

---

## 📌 Final Answers

$$
\Omega_1 = \{c_1, c_2, \dots, c_{52}\}, \quad |\Omega_1| = 52
$$

$$
\Omega_2 = \{(c_i, c_j) : c_i, c_j \in \Omega_1\}, \quad |\Omega_2| = 52^2 = 2704
$$

$$
\Omega_2' = \{(c_i, c_j) : c_i \neq c_j\}, \quad |\Omega_2'| = 52 \cdot 51 = 2652
$$

---

## 🔹 Key Insight

$$
\text{With replacement: } 52^n \quad \text{vs.} \quad \text{Without replacement: } 52 \cdot 51 \cdot \dots
$$

Each elementary outcome is an **ordered sequence of drawn cards**, where the rule (with or without replacement) determines whether repetition is allowed.
