# 📘 Task 4 — Weekly Weather Observation

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

### 3. Number of Outcomes for Repeated Observations

If an experiment has \( k \) possible outcomes per trial and is repeated \( n \) times, then:

$$
|\Omega_n| = k^n
$$

---

## ✅ Problem Solution

### 🔹 Given:

- Possible weather states:
  - Sunny (S)
  - Cloudy (C)
  - Rainy (R)
- Each day has exactly one state  
- Observations are made over consecutive days  
- The **order of outcomes matters**

---

## 1️⃣ Sample Space for One Day \( \Omega_1 \)

Possible outcomes:

$$
S, C, R
$$

$$
\Omega_1 = \{S, C, R\}
$$

### Number of outcomes:

$$
|\Omega_1| = 3
$$

### Interpretation:

Each elementary outcome represents the weather on **one day**:
- \(S\): sunny  
- \(C\): cloudy  
- \(R\): rainy  

---

## 2️⃣ Sample Space for Two Days \( \Omega_2 \)

All ordered pairs:

$$
SS, SC, SR, CS, CC, CR, RS, RC, RR
$$

$$
\Omega_2 = \{SS, SC, SR, CS, CC, CR, RS, RC, RR\}
$$

### Number of outcomes:

$$
|\Omega_2| = 9 = 3^2
$$

### Interpretation:

Each elementary outcome represents the weather over **two consecutive days**:
- \(SC\): sunny on day 1, cloudy on day 2  
- \(RR\): rainy on both days  

---

## 3️⃣ Sample Space for Seven Days \( \Omega_7 \)

All ordered sequences of length 7:

$$
(s_1, s_2, s_3, s_4, s_5, s_6, s_7)
$$

where:

$$
s_i \in \{S, C, R\}
$$

$$
\Omega_7 = \{(s_1, s_2, \dots, s_7) : s_i \in \{S, C, R\}\}
$$

### Number of outcomes:

$$
|\Omega_7| = 3^7 = 2187
$$

---

### Interpretation:

Each elementary outcome represents the weather over **seven consecutive days (one week)**:
- Example: \((S, C, R, S, S, C, R)\)  
- This describes the exact weather for each day of the week  

---

## 📌 Final Answers

$$
\Omega_1 = \{S, C, R\}, \quad |\Omega_1| = 3
$$

$$
\Omega_2 = \{SS, SC, SR, CS, CC, CR, RS, RC, RR\}, \quad |\Omega_2| = 9
$$

$$
\Omega_7 = \{(s_1, \dots, s_7) : s_i \in \{S, C, R\}\}, \quad |\Omega_7| = 3^7 = 2187
$$

---

## 🔹 Key Insight

$$
|\Omega_n| = 3^n
$$

Each elementary outcome is an **ordered sequence of weather states over \( n \) days**, representing a complete description of the observed weather.
