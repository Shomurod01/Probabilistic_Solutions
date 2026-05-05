# Problem 6 — The Axiomatic Point of View in Probability

## 1. Introduction

In the previous problems, probability was approached through **observed frequencies** obtained from repeated experiments with a finite sample space. This empirical approach naturally leads to a more general and abstract framework: the **axiomatic formulation of probability**, introduced by **Andrey Kolmogorov**.

This formulation defines probability as a mathematical object that assigns a number to each event, subject to certain fundamental rules called the **Kolmogorov axioms**.

---

## 2. Kolmogorov Axioms

Let $\Omega$ be a sample space and $P$ a function assigning a number to each event $A \subseteq \Omega$. The axioms are:

### (1) Non-negativity

$$
P(A) \ge 0 \quad \text{for every event } A
$$

### (2) Normalization

$$
P(\Omega) = 1
$$

### (3) Countable Additivity (σ-additivity)

For any sequence of pairwise disjoint events $A_1, A_2, A_3, \dots$:
$$
P\left(\bigcup_{i=1}^{\infty} A_i\right) = \sum_{i=1}^{\infty} P(A_i)
$$

---

## 3. Connection with Observed Frequencies

Our earlier work with frequencies already suggested several of these properties:

### (a) Non-negativity

Observed frequencies were defined as:
$$
f(A) = \frac{n(A)}{1000}
$$
Since counts $n(A)$ are non-negative, we always had:
$$
f(A) \ge 0
$$
This directly motivates the non-negativity axiom.

---

### (b) Normalization

The total number of outcomes was 1000, so:
$$
f(\Omega) = \frac{1000}{1000} = 1
$$
Thus, the total probability of all possible outcomes must equal 1.

---

### (c) Finite Additivity

For disjoint events $A$ and $B$, we observed:
$$
f(A \cup B) = f(A) + f(B)
$$
This worked because no outcomes were counted twice.

This corresponds to **finite additivity**, which is a direct consequence of how frequencies behave in finite experiments.

---

## 4. What Goes Beyond Finite Experiments

The key new idea in the axiomatic framework is:

### Countable Additivity

In real experiments, we only deal with:

* a **finite number of outcomes**
* a **finite number of events**

Thus, we can only verify:
$$
P(A_1 \cup A_2 \cup \cdots \cup A_n) = \sum_{i=1}^{n} P(A_i)
$$

However, Kolmogorov’s third axiom extends this to **infinitely many events**:
$$
P\left(\bigcup_{i=1}^{\infty} A_i\right)
$$

---

### Why is this subtle?

* Infinite collections of events **cannot be observed experimentally**
* Frequencies are always based on **finite trials**
* Infinite sums require **limits**, which belong to analysis, not simple counting

Thus, **countable additivity is not derived from experiments**, but is introduced as a **mathematical principle** to ensure consistency in more advanced settings.

---

## 5. Why Countable Additivity Matters

This axiom becomes essential when dealing with:

* infinite sample spaces (e.g., real numbers)
* continuous probability distributions
* limits of sequences of events

Without it, probability theory would not extend beyond simple finite models.

---

## 6. Conclusion

The development from observed frequencies to axiomatic probability can be summarized as follows:

* **Empirical observations** (frequencies) suggest basic properties:

  * non-negativity
  * normalization
  * finite additivity

* These properties are formalized into axioms

* The axiomatic framework **extends beyond experiments** by introducing countable additivity, allowing probability theory to handle infinite and continuous phenomena

In this way, probability evolves from a description of experimental data into a **rigorous mathematical theory** capable of modeling a wide range of real-world and abstract situations.
