# Task 4 — Circular Permutations

## Useful Definitions and Formulas

### 1. Circular Permutation
When arranging \( n \) distinct objects around a round table, arrangements that differ only by rotation are considered identical.

The number of circular permutations is:

$$
(n - 1)!
$$

---

### 2. Treating People as a Block
When certain people must sit together, we treat them as a single unit (block), then arrange the block with the remaining individuals.

---

### 3. Opposite Positions in a Circle
For an even number of people, fixing one person determines the opposite position uniquely.

---

# Solutions

## 1. In how many ways can 8 people sit around a round table?

Using the formula for circular permutations:

$$
(8 - 1)! = 7! = 5040
$$

**Answer:** 5040 ways

---

## 2. In how many ways can they sit if two particular people must sit next to each other?

Treat the two particular people as a single block.

- Now we have:
  - 7 units total (6 individuals + 1 block)

Number of circular arrangements:

$$
(7 - 1)! = 6!
$$

Inside the block, the two people can switch places:

$$
2!
$$

Total arrangements:

$$
6! \cdot 2! = 720 \cdot 2 = 1440
$$

**Answer:** 1440 ways

---

## 3. In how many ways can they sit if those two people must sit opposite each other?

Fix one of the two people to remove rotational symmetry.

- The opposite seat is uniquely determined for the second person.
- The remaining 6 people can be arranged freely in the remaining 6 seats.

Number of ways:

$$
6! = 720
$$

**Answer:** 720 ways
