# Task 2 — Hypergeometric Model (Sampling from a Batch)

## The situation in plain words
Imagine a warehouse with **20 components**. Out of these, **5 are defective** (broken) and **15 are functional** (working). You randomly pick **4 components without replacement** (you don't put any back). You then inspect them and count how many are defective. This is a hypergeometric situation because sampling is without replacement from a finite population.

---

## 1. Describe the random experiment (step by step)

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

## 4. Provide the probability distribution (full, clear explanation)

The **probability distribution** tells us: for each possible value \( k \) (0,1,2,3,4), what is the probability \( P(X = k) \) that the sample contains exactly \( k \) defective components?

We use the **hypergeometric formula**. Let me explain it in simple words before giving the formula.

### The idea behind the formula
To find the probability of getting exactly \( k \) defectives in your sample of 4, you count:
- How many ways to choose \( k \) defective components from the 5 defectives available.
- How many ways to choose the remaining \( 4-k \) components from the 15 functional ones.
- Multiply these two numbers together. That gives the total number of **favorable samples** (samples with exactly \( k \) defectives).
- Then divide by the total number of **all possible samples** of 4 components from the 20.

That is:

\[
P(X = k) = \frac{\text{Number of favorable samples}}{\text{Total number of possible samples}}
\]

### The formula using combinations
We write this using the "choose" symbol \( \binom{a}{b} \), which means "the number of ways to pick \( b \) items from \( a \) items, without caring about the order."

\[
P(X = k) = \frac{\binom{5}{k} \times \binom{15}{4-k}}{\binom{20}{4}}
\]

Here:
- \( \binom{5}{k} \) = ways to choose \( k \) defectives from the 5 defectives.
- \( \binom{15}{4-k} \) = ways to choose the remaining \( 4-k \) components from the 15 functional ones.
- \( \binom{20}{4} \) = total ways to choose any 4 components from the 20.

### Step 1: Calculate the total number of possible samples (denominator)
\[
\binom{20}{4} = \frac{20 \times 19 \times 18 \times 17}{4 \times 3 \times 2 \times 1} = 4845
\]
So there are 4,845 different possible samples of 4 components from the 20. This number will be the same for all probabilities.

### Step 2: Calculate each probability one by one

#### For \( k = 0 \) (no defective in the sample)
- \( \binom{5}{0} = 1 \) (there is only one way to choose zero defectives – choose none)
- \( \binom{15}{4} = \frac{15 \times 14 \times 13 \times 12}{4 \times 3 \times 2 \times 1} = 1365 \) (ways to choose 4 functional components from the 15)
- Favorable samples = \( 1 \times 1365 = 1365 \)
- \( P(X=0) = \frac{1365}{4845} \approx 0.2817 \) (about 28.2%)

Interpretation: About 28% of the time, you will get zero defective components in your sample.

#### For \( k = 1 \) (exactly one defective)
- \( \binom{5}{1} = 5 \) (ways to choose 1 defective from the 5)
- \( \binom{15}{3} = \frac{15 \times 14 \times 13}{3 \times 2 \times 1} = 455 \) (ways to choose 3 functional from the 15)
- Favorable = \( 5 \times 455 = 2275 \)
- \( P(X=1) = \frac{2275}{4845} \approx 0.4696 \) (about 47.0%)

Interpretation: Getting exactly one defective is the most likely outcome – nearly half the time.

#### For \( k = 2 \) (exactly two defectives)
- \( \binom{5}{2} = \frac{5 \times 4}{2 \times 1} = 10 \)
- \( \binom{15}{2} = \frac{15 \times 14}{2} = 105 \)
- Favorable = \( 10 \times 105 = 1050 \)
- \( P(X=2) = \frac{1050}{4845} \approx 0.2167 \) (21.7%)

#### For \( k = 3 \) (exactly three defectives)
- \( \binom{5}{3} = \frac{5 \times 4 \times 3}{3 \times 2 \times 1} = 10 \) (same as choosing 2 to leave out)
- \( \binom{15}{1} = 15 \)
- Favorable = \( 10 \times 15 = 150 \)
- \( P(X=3) = \frac{150}{4845} \approx 0.0310 \) (3.1%)

#### For \( k = 4 \) (all four defectives)
- \( \binom{5}{4} = 5 \) (ways to choose 4 defectives from the 5)
- \( \binom{15}{0} = 1 \) (only one way to choose zero functional components)
- Favorable = \( 5 \times 1 = 5 \)
- \( P(X=4) = \frac{5}{4845} \approx 0.00103 \) (0.1%)

### Step 3: Summary table

| \( k \) (defectives in sample) | Calculation | Probability | Approximate |
|-------------------------------|-------------|-------------|--------------|
| 0 | \( \frac{1 \times 1365}{4845} \) | \( \frac{1365}{4845} \) | 28.2% |
| 1 | \( \frac{5 \times 455}{4845} \) | \( \frac{2275}{4845} \) | 47.0% |
| 2 | \( \frac{10 \times 105}{4845} \) | \( \frac{1050}{4845} \) | 21.7% |
| 3 | \( \frac{10 \times 15}{4845} \) | \( \frac{150}{4845} \) | 3.1% |
| 4 | \( \frac{5 \times 1}{4845} \) | \( \frac{5}{4845} \) | 0.1% |

**Check:** \( 1365 + 2275 + 1050 + 150 + 5 = 4845 \), so the total probability is \( \frac{4845}{4845} = 1 \). Good.

---

## 5. Explain what a "success" means in this model

In hypergeometric terminology, a **success** is simply the outcome you are counting. It does **not** mean "good" or "desirable" in everyday language.

Here, we are counting **defective components**. Therefore:
- **Success** = selecting a defective component.
- **Failure** = selecting a functional component.

So the random variable \( X \) counts the number of successes (defectives) in the sample. That is all it means.

---

## Final summary

You have 20 parts (5 bad, 15 good). You randomly pick 4 without replacement. The number of bad parts in your sample can be 0,1,2,3,4. The hypergeometric formula gives the probability for each. Most likely you get 1 bad (47%). Getting 0 bad happens 28% of the time, 2 bad 22%, 3 bad 3%, and 4 bad only 0.1%. A "success" in this model means picking a bad part – the thing you are counting.
