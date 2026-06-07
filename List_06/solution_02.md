# Probability Operations — Step by Step

> Based on the discrete distribution from Task 2:
> P(X=−1)=0.15, P(X=0)=0.20, P(X=2)=0.25, P(X=4)=0.25, P(X=6)=0.15

---

## Reference Table

| x    | P(X = x) | Meaning                  |
|------|----------|--------------------------|
| −1   | 0.15     | 15% chance X equals −1  |
| 0    | 0.20     | 20% chance X equals 0   |
| 2    | 0.25     | 25% chance X equals 2   |
| 4    | 0.25     | 25% chance X equals 4   |
| 6    | 0.15     | 15% chance X equals 6   |
| **Total** | **1.00** | **must always sum to 1** |

---

## Part 1 — Adding Probabilities

### What addition answers: "OR" questions

You add probabilities when you want to know the chance that **one thing OR another thing** happens, and those two things **cannot both happen at the same time** (mutually exclusive).

### The direction addition pushes the number

> Addition **makes the number bigger** — you are covering more outcomes.
> But the result can **never exceed 1.00**.

---

### Step-by-step examples

#### Example 1 — P(X = 2 OR X = 4)

**Step 1.** Write down what you want.

```
P(X = 2 OR X = 4)
```

**Step 2.** Check: can X equal 2 and 4 at the same time? No — X is a single number. They are mutually exclusive.

**Step 3.** Look up each probability from the table.

```
P(X = 2) = 0.25
P(X = 4) = 0.25
```

**Step 4.** Add them.

```
0.25 + 0.25 = 0.50
```

**Step 5.** Interpret.

```
There is a 50% chance that X lands on either 2 or 4.
```

---

#### Example 2 — P(X = −1 OR X = 0 OR X = 6)

**Step 1.** Write down what you want.

```
P(X = −1 OR X = 0 OR X = 6)
```

**Step 2.** All three are mutually exclusive values of X. Safe to add.

**Step 3.** Look up each probability.

```
P(X = −1) = 0.15
P(X =  0) = 0.20
P(X =  6) = 0.15
```

**Step 4.** Add them all.

```
0.15 + 0.20 + 0.15 = 0.50
```

**Step 5.** Interpret.

```
There is a 50% chance X takes one of these three values.
```

---

#### Example 3 — P(X ≤ 0) using addition

**Step 1.** Write out which values satisfy X ≤ 0.

```
X = −1  and  X = 0
```

**Step 2.** Look up their probabilities.

```
P(X = −1) = 0.15
P(X =  0) = 0.20
```

**Step 3.** Add.

```
0.15 + 0.20 = 0.35
```

**Step 4.** Confirm using the CDF: F(0) = 0.35. ✓

---

#### Example 4 — P(X ≥ 4) using addition

**Step 1.** Which values satisfy X ≥ 4?

```
X = 4  and  X = 6
```

**Step 2.** Look up probabilities.

```
P(X = 4) = 0.25
P(X = 6) = 0.15
```

**Step 3.** Add.

```
0.25 + 0.15 = 0.40
```

**Step 4.** Alternatively: 1 − P(X ≤ 2) = 1 − 0.60 = 0.40. Both routes give the same answer. ✓

---

#### Example 5 — All five values add to 1

**Step 1.** Add every probability in the table.

```
0.15 + 0.20 + 0.25 + 0.25 + 0.15
```

**Step 2.** Add left to right.

```
0.15 + 0.20 = 0.35
0.35 + 0.25 = 0.60
0.60 + 0.25 = 0.85
0.85 + 0.15 = 1.00
```

**Step 3.** Interpret.

```
Every possible outcome is accounted for. Something must happen.
This is the first law of probability: all probabilities sum to 1.
```

---

### Golden rule for addition

| Check | What it means |
|-------|---------------|
| Result ≤ 1.00 | Valid — good |
| Result > 1.00 | Error — the events overlap; you counted something twice |
| Result = 1.00 | You have covered every possible outcome |

---

## Part 2 — Multiplying Probabilities

### What multiplication answers: "AND" questions

You multiply probabilities when you want to know the chance that **one thing AND another thing** both happen, and the two things are **independent** (one does not affect the other).

### The direction multiplication pushes the number

> Multiplication **makes the number smaller** — because you need everything to go right at once.
> Multiplying two numbers between 0 and 1 always gives a result smaller than either of them.

---

### Step-by-step examples

#### Example 1 — Two independent observations: P(X = 2 on trial 1 AND X = 4 on trial 2)

**Step 1.** Write down what you want.

```
P(first observation = 2  AND  second observation = 4)
```

**Step 2.** Are these independent? Yes — each observation of X is a fresh draw, unaffected by the other.

**Step 3.** Look up each probability.

```
P(X = 2) = 0.25
P(X = 4) = 0.25
```

**Step 4.** Multiply.

```
0.25 × 0.25 = 0.0625
```

**Step 5.** Interpret.

```
There is only a 6.25% chance that the first observation gives 2
AND the second gives 4. Much smaller than either 25% alone.
```

---

#### Example 2 — P(X = −1 on trial 1 AND X = 6 on trial 2)

**Step 1.**

```
P(first = −1  AND  second = 6)
```

**Step 2.** Independent trials. Safe to multiply.

**Step 3.**

```
P(X = −1) = 0.15
P(X =  6) = 0.15
```

**Step 4.**

```
0.15 × 0.15 = 0.0225
```

**Step 5.** Interpret.

```
Only 2.25% chance. Both are rare outcomes to begin with,
and needing both simultaneously makes it even harder.
```

---

#### Example 3 — Three independent draws: P(X = 2 three times in a row)

**Step 1.**

```
P(X=2 on trial 1  AND  X=2 on trial 2  AND  X=2 on trial 3)
```

**Step 2.** Three independent draws. Multiply all three.

**Step 3.**

```
P(X = 2) = 0.25  for each draw
```

**Step 4.**

```
0.25 × 0.25 × 0.25 = 0.015625
```

**Step 5.** Interpret.

```
Less than 1.6% chance of X = 2 three times in a row.
Each additional condition shrinks the result further.
```

---

#### Example 4 — What happens when you multiply a probability by 1

**Step 1.**

```
P(X = 2) × 1 = ?
```

**Step 2.**

```
0.25 × 1.00 = 0.25
```

**Step 3.** Interpret.

```
Multiplying by 1 (certainty) leaves the probability unchanged.
The certain event adds no new requirement.
```

---

#### Example 5 — What happens when you multiply a probability by 0

**Step 1.**

```
P(X = 2) × 0 = ?
```

**Step 2.**

```
0.25 × 0 = 0
```

**Step 3.** Interpret.

```
If one event is impossible, the combined event is also impossible.
An impossible condition wipes out any probability.
```

---

### Golden rule for multiplication

| Observation | What it means |
|-------------|---------------|
| Result is smaller than both inputs | Correct — this always happens between 0 and 1 |
| Result gets smaller with each extra condition | Correct — more requirements = harder to satisfy all |
| Result = 0 | One of the events is impossible |
| Result = input A | You multiplied by 1 — the second event is certain |

---

## Part 3 — Dividing Probabilities

### What division answers: "GIVEN THAT" questions (conditional probability)

You divide when you already know something has happened and want to update the probability of something else. This is written P(A | B), read as "probability of A given B."

The idea: B has happened, so B is now your **entire universe**. You rescale A's probability into that smaller world.

```
P(A | B) = P(A AND B) / P(B)
```

### The direction division pushes the number

> Division **makes the number bigger** — because the condition shrinks the universe,
> making everything inside that universe more likely.

---

### Step-by-step examples

#### Example 1 — P(X = 2 | X ≥ 2)

**Step 1.** Write what you want: the probability that X = 2, given you already know X is at least 2.

**Step 2.** Find the new universe: all outcomes where X ≥ 2.

```
X = 2, X = 4, X = 6
P(X ≥ 2) = 0.25 + 0.25 + 0.15 = 0.65
```

**Step 3.** Find the probability of the overlap: X = 2 AND X ≥ 2. Since X = 2 is already inside X ≥ 2:

```
P(X = 2 AND X ≥ 2) = P(X = 2) = 0.25
```

**Step 4.** Divide.

```
0.25 / 0.65 = 0.3846...  ≈  0.385
```

**Step 5.** Interpret.

```
Without any condition: P(X = 2) = 0.25 = 25%
With the condition X ≥ 2: P(X = 2 | X ≥ 2) ≈ 38.5%
The condition eliminated X = −1 and X = 0 from consideration,
so the remaining values each got a larger share.
```

---

#### Example 2 — P(X = 4 | X > 0)

**Step 1.** You know X > 0. Find the new universe.

```
X = 2, X = 4, X = 6
P(X > 0) = 0.25 + 0.25 + 0.15 = 0.65
```

**Step 2.** Find the overlap: X = 4 AND X > 0. Since X = 4 satisfies X > 0:

```
P(X = 4 AND X > 0) = P(X = 4) = 0.25
```

**Step 3.** Divide.

```
0.25 / 0.65 ≈ 0.385
```

**Step 4.** Interpret.

```
Originally P(X = 4) = 25%.
Given X > 0, it rises to about 38.5%.
Three equally-weighted outcomes remain in the universe (X=2, X=4, X=6),
but X=2 and X=4 are equally likely (0.25 each) while X=6 is less likely (0.15),
so X=4 does not reach 1/3 exactly — it gets a proportional share.
```

---

#### Example 3 — P(X = 0 | X ≤ 0)

**Step 1.** You know X ≤ 0. Find the new universe.

```
X = −1, X = 0
P(X ≤ 0) = 0.15 + 0.20 = 0.35
```

**Step 2.** Overlap: X = 0 AND X ≤ 0. X = 0 satisfies X ≤ 0:

```
P(X = 0 AND X ≤ 0) = P(X = 0) = 0.20
```

**Step 3.** Divide.

```
0.20 / 0.35 = 0.5714...  ≈  0.571
```

**Step 4.** Interpret.

```
Originally P(X = 0) = 20%.
Given X ≤ 0, there are only two possible outcomes: X = −1 (prob 0.15)
and X = 0 (prob 0.20). X = 0 is the heavier one, so it gets
more than half the probability within this restricted universe: 57.1%.
```

---

#### Example 4 — P(X = −1 | X ≤ 0)

**Step 1.** Same condition as Example 3: X ≤ 0, so P(X ≤ 0) = 0.35.

**Step 2.** Overlap:

```
P(X = −1 AND X ≤ 0) = P(X = −1) = 0.15
```

**Step 3.** Divide.

```
0.15 / 0.35 = 0.4286...  ≈  0.429
```

**Step 4.** Interpret.

```
Notice: P(X = −1 | X ≤ 0) + P(X = 0 | X ≤ 0)
     = 0.429 + 0.571
     = 1.000

Within the restricted universe {X = −1, X = 0}, the probabilities
still sum to 1. The universe is smaller, but the law still holds.
```

---

#### Example 5 — What if the condition has nothing to do with the event?

**Step 1.** Try: P(X = 2 | X ≤ 0).

**Step 2.** New universe: X ≤ 0, so only X = −1 and X = 0.

**Step 3.** Overlap: X = 2 AND X ≤ 0. X = 2 does NOT satisfy X ≤ 0:

```
P(X = 2 AND X ≤ 0) = 0
```

**Step 4.** Divide.

```
0 / 0.35 = 0
```

**Step 5.** Interpret.

```
P(X = 2 | X ≤ 0) = 0
If we know X ≤ 0, then X = 2 is completely ruled out.
The condition made an already-possible event impossible.
```

---

### Golden rule for division

| Check | What it means |
|-------|---------------|
| Result > original probability | Correct — condition made the event more likely |
| Result = 0 | Event is ruled out by the condition |
| Result = 1 | Event is the only thing that can happen given the condition |
| Result > 1 | Error — the numerator event is not a subset of the condition |
| Denominator = 0 | Undefined — you cannot condition on an impossible event |

---

## Part 4 — Connecting All Three Operations

### The same question, three different tools

Using the distribution from Task 2 throughout:

| Question | Operation | Answer |
|----------|-----------|--------|
| Chance X is 2 or 4? | Addition: 0.25 + 0.25 | 0.50 |
| Chance X = 2 on draw 1 AND X = 4 on draw 2? | Multiplication: 0.25 × 0.25 | 0.0625 |
| Chance X = 2, knowing X ≥ 2? | Division: 0.25 / 0.65 | 0.385 |

### How the number moves

```
Original P(X = 2) = 0.25

  Addition with P(X = 4):       0.25 + 0.25 = 0.50   ← number goes UP
  Multiplication with P(X = 4): 0.25 × 0.25 = 0.0625 ← number goes DOWN
  Division by P(X ≥ 2):         0.25 / 0.65 = 0.385  ← number goes UP
```

### When to use each

| You are asking... | Use |
|-------------------|-----|
| This OR that (mutually exclusive) | Add |
| This AND that (independent) | Multiply |
| This, GIVEN THAT we know something | Divide |
| How likely are all outcomes together? | Add all → must equal 1 |

---

## Part 5 — Quick Verification Checks

After every calculation, check:

1. **All probabilities are between 0 and 1** — no negatives, no values above 1.
2. **All mutually exclusive outcomes add to 1** — the full PMF sums to 1.00.
3. **Multiplication results are smaller than both inputs** — always, when inputs are in (0,1).
4. **Conditional probabilities within a restricted universe also sum to 1** — divide the restricted outcomes by the same denominator and check the total.

### Verification using Task 2 values

```
Full PMF check:
0.15 + 0.20 + 0.25 + 0.25 + 0.15 = 1.00  ✓

Conditional universe X ≥ 2 check:
P(X=2 | X≥2) + P(X=4 | X≥2) + P(X=6 | X≥2)
= 0.25/0.65 + 0.25/0.65 + 0.15/0.65
= 0.3846 + 0.3846 + 0.2308
= 1.0000  ✓

Multiplication shrinks check:
0.25 × 0.15 = 0.0375
0.0375 < 0.25  ✓
0.0375 < 0.15  ✓
```

---

*Distribution: X ∈ {−1, 0, 2, 4, 6} with P = {0.15, 0.20, 0.25, 0.25, 0.15}*
