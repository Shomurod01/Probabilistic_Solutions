# Problem 6 — Axiomatic Formulation of Probability (Step-by-Step)

## Step 1 — Starting Point: Experiments and Frequencies

In the previous problems, probability was not introduced directly. Instead, we worked with:

* a **finite sample space**
  $$
  \Omega = {1,2,3,4,5,6}
  $$

* **observed frequencies**
  $$
  f(A) = \frac{n(A)}{1000}
  $$

These frequencies describe how often an event occurs in repeated trials.

---

## Step 2 — From Frequencies to a General Rule

From calculations, we observed:

* $f(A) \ge 0$
* $f(\Omega) = 1$
* for disjoint events:
  $$
  f(A \cup B) = f(A) + f(B)
  $$

These properties appeared naturally from counting outcomes.

This suggests that we can define a general function (called probability) with the same properties.

---

## Step 3 — Introducing Probability

We now replace observed frequency $f(A)$ with an abstract function:

$$
P(A)
$$

This function assigns a number to every event $A \subseteq \Omega$.

---

## Step 4 — Kolmogorov Axioms

The function $P$ must satisfy the following rules:

### (1) Non-negativity

$$
P(A) \ge 0
$$

**Explanation:**
Frequencies were always non-negative because counts cannot be negative.

---

### (2) Normalization

$$
P(\Omega) = 1
$$

**Explanation:**
The whole sample space always occurred in every trial:
$$
f(\Omega) = 1
$$

---

### (3) Countable Additivity

For disjoint events $A_1, A_2, A_3, \dots$:
$$
P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)
$$

---

## Step 5 — What We Already Observed

From earlier problems, we already had:

### (a) Non-negativity

$$
f(A) \ge 0
$$

### (b) Normalization

$$
f(\Omega) = 1
$$

### (c) Finite Additivity

For disjoint events:
$$
f(A \cup B) = f(A) + f(B)
$$

These come directly from counting and experiments.

---

## Step 6 — What Is New

The new idea is:

### Countable (infinite) additivity

In experiments, we only handled **finite unions**:
$$
A_1 \cup A_2 \cup \cdots \cup A_n
$$

But the axiom states:
$$
A_1 \cup A_2 \cup A_3 \cup \cdots
$$

This is an **infinite union**.

---

## Step 7 — Why This Is More Subtle

This property is not directly observed because:

* experiments are always **finite**
* we only perform a **finite number of trials**
* we only combine a **finite number of events**

Also:

* infinite sums require limits
* limits belong to mathematical analysis, not simple counting

Therefore, this axiom is **not derived from experiments**, but added for mathematical completeness.

---

## Step 8 — Why Countable Additivity Is Needed

It allows probability to work in more advanced cases:

* infinite sample spaces
* continuous models
* limits of sequences of events

Without this, probability theory would remain limited to simple finite cases.

---

## Step 9 — Final Connection

We now understand the three levels:

### 1. Outcomes and events

* outcomes: single results
* events: sets of outcomes

### 2. Observed frequencies

* based on experiments
* approximate behavior

### 3. Probability (axiomatic)

* abstract mathematical function
* follows strict rules (axioms)
* extends beyond experiments

---

## Final Statement

The axiomatic formulation of probability is a natural extension of observed frequencies:

* non-negativity, normalization, and finite additivity come directly from experiments
* countable additivity goes beyond experiments and allows probability to handle infinite and continuous situations

Thus, probability becomes a **rigorous mathematical theory** built on simple empirical observations.
