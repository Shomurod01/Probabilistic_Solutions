# 📘 Task 1 — Coin Tossing

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

### 3. Number of Outcomes for Coin Tossing

If a fair coin is tossed \( n \) times, then the number of possible outcomes is:

$$
|\Omega_n| = 2^n
$$

Each toss has 2 possible results (H or T), and outcomes are ordered.

---

## ✅ Problem Solution

### 🔹 Given:

- A fair coin is tossed
- Possible outcomes: Heads (H), Tails (T)
- The **order of outcomes matters**

---

## 1️⃣ Sample Space for One Toss \( \Omega_1 \)

Possible outcomes:

$$
H, T
$$

$$
\Omega_1 = \{H, T\}
$$

### Number of outcomes:

$$
|\Omega_1| = 2
$$

### Interpretation:

Each elementary outcome represents the result of **one coin toss**:
- \(H\): heads  
- \(T\): tails  

---

## 2️⃣ Sample Space for Two Tosses \( \Omega_2 \)

All ordered pairs:

$$
HH, HT, TH, TT
$$

$$
\Omega_2 = \{HH, HT, TH, TT\}
$$

### Number of outcomes:

$$
|\Omega_2| = 4 = 2^2
$$

### Interpretation:

Each elementary outcome represents the result of **two ordered coin tosses**:
- \(HT\): first toss heads, second toss tails  
- \(TH\): first toss tails, second toss heads  

---

## 3️⃣ Sample Space for Three Tosses \( \Omega_3 \)

All ordered triples:

$$
HHH, HHT, HTH, HTT, THH, THT, TTH, TTT
$$

$$
\Omega_3 = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}
$$

### Number of outcomes:

$$
|\Omega_3| = 8 = 2^3
$$

### Interpretation:

Each elementary outcome represents the result of **three ordered coin tosses**:
- \(HTT\): heads, tails, tails  
- \(THH\): tails, heads, heads  

---

## 📌 Final Answers

$$
\Omega_1 = \{H, T\}, \quad |\Omega_1| = 2
$$

$$
\Omega_2 = \{HH, HT, TH, TT\}, \quad |\Omega_2| = 4
$$

$$
\Omega_3 = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}, \quad |\Omega_3| = 8
$$

---

## 🔹 Key Insight

$$
|\Omega_n| = 2^n
$$

Each elementary outcome is an **ordered sequence of \( n \) coin toss results**.
