# Task 2 — Hypergeometric Model

## The situation in plain words
Imagine a warehouse with **20 components**. Out of these, **5 are defective** (broken) and **15 are functional** (working). You randomly pick **4 components without replacement** (you don't put any back). You then inspect them and count how many are defective. This is a hypergeometric situation because sampling is without replacement from a finite population.

---

## 1. Describe the random experiment

- Start with a batch of 20 components: exactly 5 defective, 15 functional. They are mixed together.
- Randomly select 4 components. "Randomly" means every possible group of 4 has the same chance.
- Selection is **without replacement** – once a component is picked, it is not returned to the batch. So the same component cannot be chosen twice.
- After picking, inspect each selected component and classify it as defective or functional.
- The outcome is the set of 4 components you got, but we only care about the **number of defective components** in that sample.

Because you do not replace items, the probability of picking a defective changes after each draw. That is why we use the hypergeometric model, not the binomial model.

---

## 2. Define the random variable \( X \)

A random variable is a number that comes from the experiment and can change each time you repeat it.

Here:

\[
X = \text{the number of defective components in the sample of 4}
\]

Examples:
- If the sample has 0 defective and 4 functional, then \( X = 0 \).
- If it has 1 defective and 3 functional, then \( X = 1 \).
- And so on.

---

## 3. Determine the possible values of \( X \)

Think about the smallest and largest number of defectives you could get in a sample of 4.

- **Smallest possible**: 0 defectives (if you pick only functional ones).
- **Largest possible**: 4 defectives (you pick 4 components, and there are 5 defectives in total, so you could get all 4 as defectives). You cannot get 5 because you only pick 4.

So the possible values are:

\[
X \in \{0, 1, 2, 3, 4\}
\]

---

## 4. Provide the probability distribution

We use the hypergeometric formula:

\[
P(X = k) = \frac{\binom{5}{k} \binom{15}{4-k}}{\binom{20}{4}}, \quad k = 0,1,2,3,4
\]

Where \(\binom{20}{4} = 4845\) is the total number of ways to choose any 4 components from 20.

**Results:**

- \( P(X=0) = \frac{1 \times 1365}{4845} \approx 0.2817 \) (28.2%)
- \( P(X=1) = \frac{5 \times 455}{4845} \approx 0.4696 \) (47.0%)
- \( P(X=2) = \frac{10 \times 105}{4845} \approx 0.2167 \) (21.7%)
- \( P(X=3) = \frac{10 \times 15}{4845} \approx 0.0310 \) (3.1%)
- \( P(X=4) = \frac{5 \times 1}{4845} \approx 0.00103 \) (0.1%)

These probabilities add up to 1 (4845/4845). The most likely outcome is 1 defective (nearly half the time), while 4 defectives is very rare.
## 5. Explain what a "success" means in this model

In hypergeometric terminology, a **success** is simply the outcome you are counting. It does **not** mean "good" or "desirable" in everyday language.

Here, we are counting **defective components**. Therefore:
- **Success** = selecting a defective component.
- **Failure** = selecting a functional component.

So the random variable \( X \) counts the number of successes (defectives) in the sample. That is all it means.

---

## Final summary

You have 20 parts (5 bad, 15 good). You randomly pick 4 without replacement. The number of bad parts in your sample can be 0,1,2,3,4. The hypergeometric formula gives the probability for each. Most likely you get 1 bad (47%). Getting 0 bad happens 28% of the time, 2 bad 22%, 3 bad 3%, and 4 bad only 0.1%. A "success" in this model means picking a bad part – the thing you are counting.
