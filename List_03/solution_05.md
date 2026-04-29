# Task 5 — Multinomial Model (Categories of Outcomes)

## Given

- A die is rolled 5 times.
- Each result is grouped into 3 categories:
  - Small (1–2) → probability \( \frac{1}{3} \)
  - Medium (3–4) → probability \( \frac{1}{3} \)
  - Large (5–6) → probability \( \frac{1}{3} \)

---

## 1. Description of the Random Experiment

We roll a fair die 5 times.

Instead of recording exact numbers, we group each result into:
- Small
- Medium
- Large

At the end, we count how many times each category appears.

So the result looks like:
- number of small outcomes,
- number of medium outcomes,
- number of large outcomes.

---

## 2. Sample Space \( \Omega \)

The sample space contains all possible ways to distribute 5 rolls into 3 categories.

$$
\Omega = \{ (x_1, x_2, x_3) \mid x_1 + x_2 + x_3 = 5,\ x_i \ge 0 \}
$$

where:
- \( x_1 \): number of small outcomes  
- \( x_2 \): number of medium outcomes  
- \( x_3 \): number of large outcomes  

Example:
- \( (2,1,2) \) means:
  - 2 small, 1 medium, 2 large

---

## 3. Multinomial Distribution

We define random variables:
- \( X_1 \): number of small outcomes  
- \( X_2 \): number of medium outcomes  
- \( X_3 \): number of large outcomes  

Then:

$$
(X_1, X_2, X_3) \sim \text{Multinomial}(5, \tfrac{1}{3}, \tfrac{1}{3}, \tfrac{1}{3})
$$

The probability is:

$$
P(X_1 = x_1, X_2 = x_2, X_3 = x_3)
= \frac{5!}{x_1! \, x_2! \, x_3!} \left(\frac{1}{3}\right)^5
$$

---

## 4. Worked Example (Step-by-Step)

**Question:** What is the probability of getting  
2 small, 1 medium, and 2 large?

So:
$$
(x_1, x_2, x_3) = (2,1,2)
$$

### Step 1: Use the formula

$$
P = \frac{5!}{2! \, 1! \, 2!} \left(\frac{1}{3}\right)^5
$$

### Step 2: Calculate factorials

$$
5! = 120,\quad 2! = 2,\quad 1! = 1
$$

$$
P = \frac{120}{2 \cdot 1 \cdot 2} \left(\frac{1}{3}\right)^5
$$

### Step 3: Simplify

$$
P = \frac{120}{4} \cdot \frac{1}{243}
= 30 \cdot \frac{1}{243}
$$

$$
P = \frac{30}{243} = \frac{10}{81}
$$

---

## Final Summary

- We roll a die 5 times and group results into 3 categories.
- The outcome is the number of times each category appears.
- The sample space includes all triples that sum to 5.
- The distribution is multinomial with equal probabilities.
- We can calculate probabilities using the multinomial formula.
