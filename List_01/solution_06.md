# 📘 Task 6 — Events and Probabilities in Coin Tossing

## 🔹 Useful Definitions and Formulas

### 1. Probability of an Event (Equally Likely Outcomes)

If all outcomes are equally likely, then:

$$
P(A) = \frac{|A|}{|\Omega|}
$$

---

### 2. Sample Space Size for Coin Tossing

For \( n \) coin tosses:

$$
|\Omega_n| = 2^n
$$

---

### 3. Complement of an Event

$$
P(A^c) = 1 - P(A)
$$

---

## ✅ Problem Solution

### 🔹 Given:

- A fair coin  
- Outcomes: \(H\) (heads), \(T\) (tails)  
- All elementary outcomes are **equally likely**

---

# 1️⃣ Assigning Probabilities

## 🔸 One Toss \( \Omega_1 \)

$$
\Omega_1 = \{H, T\}, \quad |\Omega_1| = 2
$$

Each outcome:

$$
P(H) = P(T) = \frac{1}{2}
$$

---

## 🔸 Two Tosses \( \Omega_2 \)

$$
\Omega_2 = \{HH, HT, TH, TT\}, \quad |\Omega_2| = 4
$$

Each outcome:

$$
P(\omega) = \frac{1}{4}
$$

---

## 🔸 Three Tosses \( \Omega_3 \)

$$
\Omega_3 = \{HHH, HHT, HTH, HTT, THH, THT, TTH, TTT\}, \quad |\Omega_3| = 8
$$

Each outcome:

$$
P(\omega) = \frac{1}{8}
$$

---

# 2️⃣ One Coin Toss

## 🔸 Event \( A_1 \): result is heads

$$
A_1 = \{H\}
$$

$$
P(A_1) = \frac{1}{2}
$$

---

## 🔸 Event \( B_1 \): result is tails

$$
B_1 = \{T\}
$$

$$
P(B_1) = \frac{1}{2}
$$

---

## 🔸 Event \( C_1 \): result is not tails

$$
C_1 = \{H\}
$$

$$
P(C_1) = \frac{1}{2}
$$

---

# 3️⃣ Two Coin Tosses

## 🔸 Event \( A_2 \): exactly one head

$$
A_2 = \{HT, TH\}
$$

$$
P(A_2) = \frac{2}{4} = \frac{1}{2}
$$

---

## 🔸 Event \( B_2 \): at least one head

$$
B_2 = \{HH, HT, TH\}
$$

$$
P(B_2) = \frac{3}{4}
$$

---

## 🔸 Event \( C_2 \): same result

$$
C_2 = \{HH, TT\}
$$

$$
P(C_2) = \frac{2}{4} = \frac{1}{2}
$$

---

# 4️⃣ Three Coin Tosses

## 🔸 Event \( A_3 \): exactly two heads

$$
A_3 = \{HHT, HTH, THH\}
$$

$$
P(A_3) = \frac{3}{8}
$$

---

## 🔸 Event \( B_3 \): at least one tail

Using complement:

$$
B_3 = \Omega_3 \setminus \{HHH\}
$$

$$
P(B_3) = 1 - \frac{1}{8} = \frac{7}{8}
$$

---

## 🔸 Event \( C_3 \): all same result

$$
C_3 = \{HHH, TTT\}
$$

$$
P(C_3) = \frac{2}{8} = \frac{1}{4}
$$

---

# 📌 Final Answers

## One Toss

$$
P(A_1) = \frac{1}{2}, \quad P(B_1) = \frac{1}{2}, \quad P(C_1) = \frac{1}{2}
$$

---

## Two Tosses

$$
P(A_2) = \frac{1}{2}, \quad P(B_2) = \frac{3}{4}, \quad P(C_2) = \frac{1}{2}
$$

---

## Three Tosses

$$
P(A_3) = \frac{3}{8}, \quad P(B_3) = \frac{7}{8}, \quad P(C_3) = \frac{1}{4}
$$

---

## 🔹 Key Insight

$$
P(A) = \frac{|A|}{|\Omega|}
$$

In finite sample spaces with equally likely outcomes, probability reduces to **counting favorable outcomes**.
