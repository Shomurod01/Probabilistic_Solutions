# Task 3 — Geometric Model (Waiting for the First Event)

## Useful Definitions and Formulas

### 1. Geometric Distribution
The geometric model describes the number of independent trials needed to observe the **first success**.

If:
- Each trial has probability \( p \) of success,
- Trials are independent,

then the probability that the first success occurs on trial \( k \) is:

$$
P(X = k) = (1 - p)^{k - 1} \cdot p
$$

for \( k = 1, 2, 3, \dots \)

---

### 2. Independence
Each trial does not affect the others, and probabilities remain constant across trials.

---

# Given

- Each printed page is inspected sequentially.
- Each page has probability \( p \) of containing an error.
- Pages are independent.

---

# Solutions

## 1. Describe the random experiment

The experiment consists of:
- Observing consecutive printed pages one by one,
- Each page is classified as:
  - Error (E)
  - No error (N)
- The process continues until the **first page with an error** is observed.

This is a sequence of independent Bernoulli trials where we stop at the first success (error).

---

## 2. Determine the sample space \( \Omega \)

Each outcome corresponds to the position of the first error.

Possible outcomes are sequences where:
- The first \( k - 1 \) pages have no error,
- The \( k \)-th page contains an error.

Thus:

$$
\Omega = \{ E,\ NE,\ NNE,\ NNNE,\ \dots \}
$$

Formally:

$$
\Omega = \{ N^{k-1}E \mid k = 1, 2, 3, \dots \}
$$

---

## 3. Provide the probability distribution

Let \( X \) be the number of the page on which the first error appears.

Then \( X \) follows a geometric distribution:

$$
P(X = k) = (1 - p)^{k - 1} \cdot p
$$

for:

$$
k = 1, 2, 3, \dots
$$

---

## 4. Specify what is considered a success

In this model:

- A **success** is defined as a **page containing a printing error**.

Thus:
- Success probability = \( p \)
- Failure probability = \( 1 - p \)

The random variable \( X \) counts the trial number on which the first success occurs.

---
