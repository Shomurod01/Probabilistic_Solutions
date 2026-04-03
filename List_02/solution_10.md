# Task 10 — Urn Models

## Useful Definitions and Formulas

### 1. Combinations (Without Order)
When selecting objects without regard to order:

$$
\binom{n}{k} = \frac{n!}{k!(n - k)!}
$$

---

### 2. Counting by Cases
When conditions are imposed (e.g., exactly 2 red balls), we:
- Choose items satisfying the condition
- Choose remaining items from the rest
- Multiply the results

---

### 3. Ordered Outcomes
When order matters, we count permutations of the selected items or sequences of categories.

---

# Given

Urn contains:
- 5 red balls (R)
- 4 blue balls (B)
- 3 green balls (G)

Total balls:

$$
5 + 4 + 3 = 12
$$

---

# Solutions

## 1. Three balls are drawn without replacement. How many samples are possible if order is ignored?

We are choosing 3 balls from 12 without regard to order:

$$
\binom{12}{3}
$$

Compute:

$$
\binom{12}{3} = \frac{12 \cdot 11 \cdot 10}{3 \cdot 2 \cdot 1} = 220
$$

**Answer:** 220 samples

---

## 2. How many samples contain exactly two red balls?

- Choose 2 red balls from 5:

$$
\binom{5}{2}
$$

- Choose 1 non-red ball from the remaining 7 balls (4 blue + 3 green):

$$
\binom{7}{1}
$$

Multiply:

$$
\binom{5}{2} \cdot \binom{7}{1}
$$

Compute:

$$
\binom{5}{2} = 10, \quad \binom{7}{1} = 7
$$

$$
10 \cdot 7 = 70
$$

**Answer:** 70 samples

---

## 3. Three balls are drawn and the order of colors is recorded. How many outcomes are possible?

We count color sequences of length 3 using colors:
- R (red)
- B (blue)
- G (green)

Each position has 3 choices, and repetition is allowed:

$$
3^3 = 27
$$

**Answer:** 27 outcomes

---

## 4. How many outcomes contain exactly two red balls?

We count ordered color sequences of length 3 with exactly 2 Rs.

### Step 1: Choose positions of the 2 red balls
Number of ways to choose positions:

$$
\binom{3}{2} = 3
$$

### Step 2: Choose the third color (non-red)
The remaining position can be:
- Blue (B) or Green (G): 2 choices

### Step 3: Multiply

$$
\binom{3}{2} \cdot 2 = 3 \cdot 2 = 6
$$

**Answer:** 6 outcomes
