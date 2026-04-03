# Task 2 — Permutations

## Useful Definitions and Formulas

### 1. Permutation of n distinct elements
The number of ways to arrange \( n \) distinct objects:

$$
P(n) = n!
$$

---

### 2. Permutation of n elements with a restriction (fixed positions or grouping)
When certain elements must be treated as a single block, we reduce the number of objects and multiply by internal arrangements of the block.

---

### 3. Basic counting principles
- Multiplication principle: if one step can be done in \( a \) ways and another in \( b \) ways, total ways = \( a \cdot b \).
- Complement principle:  
  \[
  \text{(total arrangements)} - \text{(restricted arrangements)}
  \]

---

# Solutions

## 1. In how many ways can 8 different books be arranged on a shelf?

All books are distinct and order matters.

We use permutation:

$$
8! = 40320
$$

**Answer:** 40320 ways

---

## 2. In how many ways can 8 people sit in a row if two particular people must sit next to each other?

Let the two particular people be treated as a single block.

- Treat them as one unit → now we have:
  - 7 units total (6 individuals + 1 block)
- Arrange these 7 units:

$$
7!
$$

- Inside the block, the two people can switch places:

$$
2!
$$

Total arrangements:

$$
7! \cdot 2! = 5040 \cdot 2 = 10080
$$

**Answer:** 10080 ways

---

## 3. In how many ways can they sit if those two people must not sit next to each other?

Use the complement principle.

- Total arrangements of 8 people:

$$
8! = 40320
$$

- Arrangements where the two people sit together (from previous part):

$$
7! \cdot 2! = 10080
$$

- Subtract:

$$
8! - (7! \cdot 2!) = 40320 - 10080 = 30240
$$

**Answer:** 30240 ways

---

## 4. In how many ways can 10 questions in a test be ordered if the first question is fixed?

- The first question is fixed → only 1 choice for position 1.
- Remaining 9 questions can be arranged freely:

$$
9! = 362880
$$

**Answer:** 362880 ways
