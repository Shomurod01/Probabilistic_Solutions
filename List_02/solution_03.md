# Task 3 — Permutations with Repeated Elements

## Useful Definitions and Formulas

### 1. Permutations with Repeated Elements
If a set has \( n \) total elements, where:
- \( n_1 \) elements are identical of one type,
- \( n_2 \) elements are identical of another type, etc.,

then the number of distinct permutations is:

$$
\frac{n!}{n_1! \cdot n_2! \cdots n_k!}
$$

---

### 2. Strategy for Conditional Arrangements
When a condition is imposed (e.g., starting with a specific letter):
- Fix the required element first,
- Then count permutations of the remaining elements.

---

# Solutions

## 1. How many distinct arrangements of the word MISSISSIPPI are possible?

Count letter frequencies:
- M: 1
- I: 4
- S: 4
- P: 2

Total letters:

$$
11
$$

Using the formula for permutations with repeated elements:

$$
\frac{11!}{4! \cdot 4! \cdot 2! \cdot 1!}
$$

Compute:

$$
\frac{11!}{4! \cdot 4! \cdot 2!} = \frac{39916800}{24 \cdot 24 \cdot 2} = \frac{39916800}{1152} = 34650
$$

**Answer:** 34650

---

## 2. How many distinct arrangements of STATISTICS are possible?

Count letter frequencies:
- S: 3
- T: 3
- A: 1
- I: 2
- C: 1

Total letters:

$$
10
$$

Apply the formula:

$$
\frac{10!}{3! \cdot 3! \cdot 2! \cdot 1! \cdot 1!}
$$

Compute:

$$
\frac{10!}{3! \cdot 3! \cdot 2!} = \frac{3628800}{6 \cdot 6 \cdot 2} = \frac{3628800}{72} = 50400
$$

**Answer:** 50400

---

## 3. How many of the arrangements of STATISTICS start with the letter S?

We fix one S in the first position.

Remaining letters after fixing one S:
- S: 2 remaining
- T: 3
- A: 1
- I: 2
- C: 1

Total remaining letters:

$$
9
$$

Now compute permutations of the remaining letters:

$$
\frac{9!}{2! \cdot 3! \cdot 2! \cdot 1! \cdot 1!}
$$

Compute:

$$
\frac{9!}{2! \cdot 3! \cdot 2!} = \frac{362880}{2 \cdot 6 \cdot 2} = \frac{362880}{24} = 15120
$$

**Answer:** 15120
