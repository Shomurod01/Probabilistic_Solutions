# 📘 Task 10 — Events and Probabilities in Buffon's Needle Experiment

## 🔹 Useful Definitions and Formulas

### 1. Continuous Probability

If the sample space is continuous:

$$
P(A) = \frac{\text{area of } A}{\text{area of } \Omega}
$$

---

### 2. Sample Space

From Task 5:

$$
\Omega = \{(x, \theta) : x \in [0, d/2], \; \theta \in [0, \pi/2]\}
$$

Total area:

$$
|\Omega| = \frac{d}{2} \cdot \frac{\pi}{2} = \frac{d\pi}{4}
$$

---

### 3. Intersection Condition

The needle intersects a line if:

$$
x \le \frac{L}{2}\sin\theta
$$

---

## ✅ Problem Solution

### 🔹 Given:

- \( X \sim U[0, d/2] \), \( \theta \sim U[0, \pi/2] \)  
- Independent variables  
- \( L \le d \)

---

# 1️⃣ Event \( A \): needle intersects a line

$$
A = \{(x,\theta) : x \le \tfrac{L}{2}\sin\theta\}
$$

$$
P(A) = \frac{1}{|\Omega|} \int_0^{\pi/2} \int_0^{(L/2)\sin\theta} dx\, d\theta
$$

$$
= \frac{1}{|\Omega|} \int_0^{\pi/2} \frac{L}{2}\sin\theta \, d\theta
$$

$$
= \frac{L/2}{d\pi/4} = \frac{2L}{d\pi}
$$

---

# 2️⃣ Event \( B \): no intersection

$$
B = A^c
$$

$$
P(B) = 1 - P(A) = 1 - \frac{2L}{d\pi}
$$

---

# 3️⃣ Event \( C \): angle < \( \pi/6 \)

$$
C = \{\theta < \pi/6\}
$$

$$
P(C) = \frac{\pi/6}{\pi/2} = \frac{1}{3}
$$

---

# 4️⃣ Event \( D \): distance < \( d/4 \)

$$
D = \{x < d/4\}
$$

$$
P(D) = \frac{d/4}{d/2} = \frac{1}{2}
$$

---

# 5️⃣ Event \( E \): intersection and \( \theta > \pi/4 \)

$$
E = \{x \le \tfrac{L}{2}\sin\theta, \; \theta > \pi/4\}
$$

$$
P(E) = \frac{1}{|\Omega|} \int_{\pi/4}^{\pi/2} \int_0^{(L/2)\sin\theta} dx\, d\theta
$$

$$
= \frac{1}{|\Omega|} \int_{\pi/4}^{\pi/2} \frac{L}{2}\sin\theta \, d\theta
$$

$$
= \frac{L\sqrt{2}}{d\pi}
$$

---

# 6️⃣ Additional Event \( F \): angle greater than \( \pi/3 \)

Define:

$$
F = \{\theta > \pi/3\}
$$

$$
P(F) = \frac{\pi/2 - \pi/3}{\pi/2} = \frac{1}{3}
$$

---

# 📌 Final Answers

$$
P(A) = \frac{2L}{d\pi}
$$

$$
P(B) = 1 - \frac{2L}{d\pi}
$$

$$
P(C) = \frac{1}{3}
$$

$$
P(D) = \frac{1}{2}
$$

$$
P(E) = \frac{L\sqrt{2}}{d\pi}
$$

$$
P(F) = \frac{1}{3}
$$

---

## 🔹 Key Insight

$$
P(A) = \frac{\text{area of favorable region}}{\text{total area}}
$$

Buffon's needle is a **continuous probability model**, where probabilities are computed using **integration over geometric regions**.
