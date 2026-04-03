# Task 2 — Hypergeometric Model (Sampling from a Batch)

## Useful Definitions and Formulas

### 1. Hypergeometric Model
Used when:
- Sampling is done **without replacement**,
- The population is finite,
- Each item is classified as either success or failure.

---

### 2. Hypergeometric Probability Formula

If:
- \( N \) = total population size  
- \( K \) = number of success states in the population  
- \( n \) = sample size  
- \( X \) = number of successes in the sample  

Then:

$$
P(X = k) = \frac{\binom{K}{k} \binom{N - K}{n - k}}{\binom{N}{n}}
$$

---

### 3. Random Variable
A function that assigns a numerical value to each outcome of a random experiment.

---

# Given

- Total components: \( N = 20 \)
- Defective components: \( K = 5 \)
- Functional components: \( 15 \)
- Sample size: \( n = 4 \)

---

# Solutions

## 1. Describe the random experiment

The experiment consists of:
- Randomly selecting 4 components from a batch of 20,
- Selection is done **without replacement**,
- Each selected component is inspected and classified as:
  - Defective
  - Functional

Since the selection is without replacement, the probabilities change after each draw, which leads to a hypergeometric model.

---

## 2. Define the random variable \( X \)

Let:

- \( X \) = the number of defective components in the sample of 4 selected components.

---

## 3. Determine the possible values of \( X \)

The number of defective components in the sample can range from:
- Minimum: 0 defective components
- Maximum: 4 defective components (limited by sample size and available defective items)

Thus:

$$
X \in \{0, 1, 2, 3, 4\}
$$

---

## 4. Provide the probability distribution

Using the hypergeometric formula:

$$
P(X = k) = \frac{\binom{5}{k} \binom{15}{4 - k}}{\binom{20}{4}}
$$

for \( k = 0, 1, 2, 3, 4 \).

---

### Explicit probabilities:

- For \( X = 0 \):

$$
P(X = 0) = \frac{\binom{5}{0} \binom{15}{4}}{\binom{20}{4}}
$$

- For \( X = 1 \):

$$
P(X = 1) = \frac{\binom{5}{1} \binom{15}{3}}{\binom{20}{4}}
$$

- For \( X = 2 \):

$$
P(X = 2) = \frac{\binom{5}{2} \binom{15}{2}}{\binom{20}{4}}
$$

- For \( X = 3 \):

$$
P(X = 3) = \frac{\binom{5}{3} \binom{15}{1}}{\binom{20}{4}}
$$

- For \( X = 4 \):

$$
P(X = 4) = \frac{\binom{5}{4} \binom{15}{0}}{\binom{20}{4}}
$$

---

## 5. Explain what a success means in this model

In the hypergeometric model:

- A **success** is defined as selecting a **defective component**.

Thus:
- Success = defective item  
- Failure = functional item  

The random variable \( X \) counts the number of successes (defective components) in the sample.

---
