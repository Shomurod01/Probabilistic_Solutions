# 📘 Task 8 — Events and Probabilities in Card Drawing

## 🔹 Useful Definitions and Formulas

### 1. Probability of an Event (Equally Likely Outcomes)

$$
P(A) = \frac{|A|}{|\Omega|}
$$

---

### 2. Deck Properties

- Total cards: 52  
- Hearts: 13  
- Kings: 4  
- Face cards (J, Q, K): 12  
- Aces: 4  

---

### 3. Sample Space Sizes

With replacement:

$$
|\Omega_2| = 52^2
$$

Without replacement:

$$
|\Omega_2'| = 52 \cdot 51
$$

---

## ✅ Problem Solution

### 🔹 Given:

- Standard 52-card deck  
- Ordered draws  
- All outcomes are **equally likely**

---

# 1️⃣ Assigning Probabilities

## 🔸 One Draw \( \Omega_1 \)

$$
|\Omega_1| = 52, \quad P(\omega) = \frac{1}{52}
$$

---

## 🔸 Two Draws (with replacement) \( \Omega_2 \)

$$
|\Omega_2| = 52^2 = 2704, \quad P(\omega) = \frac{1}{2704}
$$

---

## 🔸 Two Draws (without replacement) \( \Omega_2' \)

$$
|\Omega_2'| = 52 \cdot 51 = 2652, \quad P(\omega) = \frac{1}{2652}
$$

---

# 2️⃣ One Card Drawn

## 🔸 Event \( A_1 \): card is a heart

$$
|A_1| = 13
$$

$$
P(A_1) = \frac{13}{52} = \frac{1}{4}
$$

---

## 🔸 Event \( B_1 \): card is a king

$$
|B_1| = 4
$$

$$
P(B_1) = \frac{4}{52} = \frac{1}{13}
$$

---

## 🔸 Event \( C_1 \): not a face card

$$
|C_1| = 52 - 12 = 40
$$

$$
P(C_1) = \frac{40}{52} = \frac{10}{13}
$$

---

# 3️⃣ Two Cards (with replacement)

## 🔸 Event \( A_2 \): both hearts

$$
P(A_2) = \frac{13}{52} \cdot \frac{13}{52} = \frac{1}{16}
$$

---

## 🔸 Event \( B_2 \): same rank

- First card: any  
- Second card: 4 cards of same rank  

$$
P(B_2) = \frac{4}{52} = \frac{1}{13}
$$

---

## 🔸 Event \( C_2 \): at least one ace

Using complement:

$$
P(C_2) = 1 - P(\text{no ace})
$$

$$
P(\text{no ace}) = \frac{48}{52} \cdot \frac{48}{52} = \left(\frac{12}{13}\right)^2
$$

$$
P(C_2) = 1 - \left(\frac{12}{13}\right)^2 = \frac{25}{169}
$$

---

# 4️⃣ Two Cards (without replacement)

## 🔸 Event \( A_3 \): both hearts

$$
P(A_3) = \frac{13}{52} \cdot \frac{12}{51} = \frac{1}{17}
$$

---

## 🔸 Event \( B_3 \): same rank

- First card: any  
- Second card: 3 remaining cards of same rank  

$$
P(B_3) = \frac{3}{51} = \frac{1}{17}
$$

---

## 🔸 Event \( C_3 \): one king and one queen

Number of favorable outcomes:

- King then Queen: \(4 \cdot 4 = 16\)  
- Queen then King: \(4 \cdot 4 = 16\)  

$$
|C_3| = 32
$$

$$
P(C_3) = \frac{32}{52 \cdot 51} = \frac{8}{663}
$$

---

# 📌 Final Answers

## One Draw

$$
P(A_1) = \frac{1}{4}, \quad P(B_1) = \frac{1}{13}, \quad P(C_1) = \frac{10}{13}
$$

---

## Two Draws (with replacement)

$$
P(A_2) = \frac{1}{16}, \quad P(B_2) = \frac{1}{13}, \quad P(C_2) = \frac{25}{169}
$$

---

## Two Draws (without replacement)

$$
P(A_3) = \frac{1}{17}, \quad P(B_3) = \frac{1}{17}, \quad P(C_3) = \frac{8}{663}
$$

---

## 🔹 Key Insight

$$
\text{With replacement: independent draws}
$$

$$
\text{Without replacement: probabilities change after each draw}
$$

Probability problems reduce to **counting favorable outcomes and understanding dependence between events**.
