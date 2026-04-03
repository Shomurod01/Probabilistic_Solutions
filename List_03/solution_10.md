# Task 10 — Multinomial Model

## Useful Definitions and Formulas

### 1. Multinomial Distribution
The multinomial distribution generalizes the binomial distribution to more than two categories.

If:
- \( n \) independent trials,
- Each trial results in one of \( k \) categories,
- Probabilities are \( p_1, p_2, \dots, p_k \),

then:

$$
P(X_1 = x_1, \dots, X_k = x_k) = \frac{n!}{x_1! x_2! \cdots x_k!} \cdot p_1^{x_1} p_2^{x_2} \cdots p_k^{x_k}
$$

subject to:

$$
x_1 + x_2 + \cdots + x_k = n
$$

---

# Given

- Number of selections:

$$
n = 6
$$

- Probabilities:
  - Strawberry: \( p_s = 0.40 \)
  - Lemon: \( p_l = 0.35 \)
  - Mint: \( p_m = 0.25 \)

We want:

- 3 strawberry
- 2 lemon
- 1 mint

---

# Solution

## Step 1: Apply the multinomial formula

$$
P = \frac{6!}{3! \cdot 2! \cdot 1!} \cdot (0.40)^3 \cdot (0.35)^2 \cdot (0.25)^1
$$

---

## Step 2: Compute the multinomial coefficient

$$
\frac{6!}{3! \cdot 2! \cdot 1!} = \frac{720}{6 \cdot 2 \cdot 1} = 60
$$

---

## Step 3: Compute probability terms

$$
(0.40)^3 = 0.064
$$

$$
(0.35)^2 = 0.1225
$$

$$
(0.25)^1 = 0.25
$$

---

## Step 4: Multiply all components

$$
P = 60 \cdot 0.064 \cdot 0.1225 \cdot 0.25
$$

First:

$$
0.064 \cdot 0.1225 = 0.00784
$$

Then:

$$
0.00784 \cdot 0.25 = 0.00196
$$

Finally:

$$
P = 60 \cdot 0.00196 = 0.1176
$$

---

# Final Answer

$$
P \approx 0.1176
$$
