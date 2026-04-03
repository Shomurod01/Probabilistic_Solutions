# Task 1 — Binomial Model (Quality Control)

## Useful Definitions and Formulas

### 1. Bernoulli Trial
An experiment with exactly two possible outcomes:
- Success (with probability \( p \))
- Failure (with probability \( 1 - p \))

---

### 2. Independent Trials
A sequence of experiments where the outcome of one trial does not affect the others.

---

### 3. Sample Space
The set of all possible outcomes of a random experiment.

---

### 4. Binomial Model
A model consisting of:
- A fixed number of independent trials \( n \),
- Each trial has two outcomes,
- Constant probability of success \( p \).

---

# Solutions

## 1. Describe the random experiment

The experiment consists of:
- Inspecting 3 consecutive screws from a production process.
- Each screw is classified as either:
  - Good (G)
  - Defective (D)
- Each inspection is independent.
- The probability that any given screw is defective is \( p \), and therefore the probability it is good is \( 1 - p \).

This is a sequence of 3 independent Bernoulli trials.

---

## 2. Determine the sample space \( \Omega \)

Each screw can be either Good (G) or Defective (D). Since 3 screws are inspected, the sample space consists of all sequences of length 3:

$$
\Omega = \{ GGG, GGD, GDG, GDD, DGG, DGD, DDG, DDD \}
$$

There are:

$$
2^3 = 8
$$

possible outcomes.

---

## 3. Specify the probabilities of the elements of the sample space

Let:
- \( P(D) = p \)
- \( P(G) = 1 - p \)

Since trials are independent, the probability of each outcome is the product of the probabilities of its components.

Examples:

- \( P(GGG) = (1 - p)^3 \)
- \( P(GGD) = (1 - p)^2 \cdot p \)
- \( P(GDG) = (1 - p) \cdot p \cdot (1 - p) \)
- \( P(DDD) = p^3 \)

In general:
- Multiply \( p \) for each defective screw
- Multiply \( (1 - p) \) for each good screw

---

## 4. Define what is considered a success in this model

A **success** is defined as:

- A screw being **defective**

Thus:
- Success probability = \( p \)
- Failure probability = \( 1 - p \)

This definition is consistent with the binomial model, where the “success” event is typically the event of interest (here, detecting a defective screw).

---
