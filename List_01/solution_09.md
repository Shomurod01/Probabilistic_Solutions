# 📘 Task 9 — Events and Probabilities in Weekly Weather Observation

## 🔹 Useful Definitions and Formulas

### 1. Probability of Independent Events

If events are independent:

$$
P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1)\cdot P(A_2)\cdot \dots \cdot P(A_n)
$$

---

### 2. Complement Rule

$$
P(A^c) = 1 - P(A)
$$

---

### 3. Binomial-Type Counting

Number of ways to choose \( k \) days out of \( n \):

$$
\binom{n}{k}
$$

---

## ✅ Problem Solution

### 🔹 Given:

- 7 independent days  
- Possible states: \( S, C, R \)  
- Each state has probability:

$$
P(S) = P(C) = P(R) = \frac{1}{3}
$$

- Sample space:

$$
|\Omega_7| = 3^7
$$

---

# 1️⃣ Event \( A \): weekend is sunny

Saturday and Sunday are both sunny:

$$
P(A) = P(S)^2 = \left(\frac{1}{3}\right)^2 = \frac{1}{9}
$$

---

# 2️⃣ Event \( B \): Wed, Thu, Fri are rainy

Three specific days are rainy:

$$
P(B) = P(R)^3 = \left(\frac{1}{3}\right)^3 = \frac{1}{27}
$$

---

# 3️⃣ Event \( C \): at least one sunny day

Use complement (no sunny days):

$$
P(C) = 1 - P(\text{no sunny days})
$$

Each day is either \(C\) or \(R\):

$$
P(\text{no sunny}) = \left(\frac{2}{3}\right)^7
$$

$$
P(C) = 1 - \left(\frac{2}{3}\right)^7
$$

---

# 4️⃣ Event \( D \): no rainy day

Each day is either \(S\) or \(C\):

$$
P(D) = \left(\frac{2}{3}\right)^7
$$

---

# 5️⃣ Event \( E \): exactly two sunny days

Choose 2 days out of 7:

$$
\binom{7}{2} = 21
$$

Probability for each such sequence:

- 2 sunny days: \( \left(\frac{1}{3}\right)^2 \)
- 5 non-sunny days: \( \left(\frac{2}{3}\right)^5 \)

Thus:

$$
P(E) = \binom{7}{2} \left(\frac{1}{3}\right)^2 \left(\frac{2}{3}\right)^5
$$

$$
P(E) = 21 \cdot \frac{1}{9} \cdot \frac{32}{243} = \frac{672}{2187}
$$

---

# 📌 Final Answers

$$
P(A) = \frac{1}{9}
$$

$$
P(B) = \frac{1}{27}
$$

$$
P(C) = 1 - \left(\frac{2}{3}\right)^7
$$

$$
P(D) = \left(\frac{2}{3}\right)^7
$$

$$
P(E) = \frac{672}{2187}
$$

---

## 🔹 Key Insight

$$
\text{Independent trials} \Rightarrow \text{multiply probabilities}
$$

$$
\text{Counting + probability} \Rightarrow \text{binomial structure}
$$

Weekly weather problems combine **independence, complements, and combinatorics**.
