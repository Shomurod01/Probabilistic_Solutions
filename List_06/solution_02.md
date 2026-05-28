# Problem 2 — Four Regions of a Sample Space
## Full Step-by-Step Explanation

---

## The Data Table

| Ticket type | S (solved 1st contact) | Sᶜ (not solved) | Total |
|---|:---:|:---:|:---:|
| T (technical) | 90 | 60 | 150 |
| Tᶜ (non-technical) | 160 | 40 | 200 |
| **Total** | **250** | **100** | **350** |

**The only rule you need for every probability in this problem:**

$$P(\text{any event}) = \frac{\text{how many tickets belong to that event}}{350 \text{ (total tickets)}}$$

---

---

# Part 1 — The Four Region Probabilities

## What are we doing and why?

We want to find the probability of each possible combination of ticket type and resolution outcome.
There are exactly **four combinations** (technical/non-technical × solved/not solved).
We call these "regions" because if you draw a rectangle and split it by rows and columns, each combination occupies its own region with no overlap.

---

## Why do we use this formula?

$$P(\text{region}) = \frac{\text{count in that region}}{350}$$

**Because we are working with equally likely outcomes.**
Each of the 350 tickets has the same chance of being selected if we pick one at random.
When all outcomes are equally likely, probability is simply:

$$P = \frac{\text{number of favourable outcomes}}{\text{total number of outcomes}}$$

This is called the **classical definition of probability**.

---

## P(T ∩ S) — Technical AND solved on first contact

### Where does the number come from?

Go to the data table:
- Row = T (technical)
- Column = S (solved on first contact)
- The cell at that intersection = **90**

Those 90 tickets are the ones that are **both** technical in nature **and** were resolved in the very first interaction with the agent.

### The calculation

$$P(T \cap S) = \frac{90}{350} \approx 0.2571$$

### What does the symbol ∩ mean?

The symbol ∩ means **"AND"** — both conditions must be true at the same time.
A ticket is in T ∩ S only if it is technical **AND** also solved. If it is technical but not solved, it does not belong here. If it is solved but not technical, it does not belong here either.

### What does 0.2571 mean?

It means: if you randomly pick one ticket from the 350, there is a **25.7% chance** you land on a ticket that is both technical and solved on first contact.

---

## P(T ∩ Sᶜ) — Technical AND NOT solved on first contact

### Where does the number come from?

Go to the data table:
- Row = T (technical)
- Column = Sᶜ (not solved on first contact)
- The cell at that intersection = **60**

Those 60 tickets are technical problems that the agent could **not** fix in the first interaction. The customer had to wait for a follow-up, escalation, or further investigation.

### The calculation

$$P(T \cap S^c) = \frac{60}{350} \approx 0.1714$$

### What does the superscript c mean?

The **c** in Sᶜ stands for **complement** — the opposite of S.
- S = solved on first contact
- Sᶜ = NOT solved on first contact

So T ∩ Sᶜ means: technical AND not solved.

### What does 0.1714 mean?

It means: if you randomly pick one ticket, there is a **17.1% chance** it is a technical ticket that was not resolved on first contact — a case that required extra work beyond the first call or chat.

---

## P(Tᶜ ∩ S) — Non-technical AND solved on first contact

### Where does the number come from?

Go to the data table:
- Row = Tᶜ (non-technical)
- Column = S (solved on first contact)
- The cell at that intersection = **160**

Those 160 tickets are non-technical issues (billing questions, account updates, general inquiries) that were fully resolved in a single interaction. This is the **largest region** — non-technical issues are usually straightforward.

### The calculation

$$P(T^c \cap S) = \frac{160}{350} \approx 0.4571$$

### What does 0.4571 mean?

It means: if you randomly pick one ticket, there is a **45.7% chance** it is a non-technical ticket that was solved on first contact. Nearly half of all tickets fall into this category — it is the most common outcome in the entire dataset.

---

## P(Tᶜ ∩ Sᶜ) — Non-technical AND NOT solved on first contact

### Where does the number come from?

Go to the data table:
- Row = Tᶜ (non-technical)
- Column = Sᶜ (not solved on first contact)
- The cell at that intersection = **40**

Those 40 tickets are non-technical issues that still could not be resolved in the first contact. Even simple tickets sometimes require manager approval, missing account information, or third-party verification.

### The calculation

$$P(T^c \cap S^c) = \frac{40}{350} \approx 0.1143$$

### What does 0.1143 mean?

It means: if you randomly pick one ticket, there is only an **11.4% chance** it is a non-technical ticket that was not solved on first contact. This is the smallest region — the rarest outcome.

---

## Summary Table

| Region | Plain English | Cell in table | Count | Probability |
|---|---|:---:|:---:|:---:|
| P(T ∩ S) | technical & solved | row T, col S | 90 | 0.2571 |
| P(T ∩ Sᶜ) | technical & not solved | row T, col Sᶜ | 60 | 0.1714 |
| P(Tᶜ ∩ S) | non-technical & solved | row Tᶜ, col S | 160 | 0.4571 |
| P(Tᶜ ∩ Sᶜ) | non-technical & not solved | row Tᶜ, col Sᶜ | 40 | 0.1143 |

---

## Verification — do they sum to 1?

$$0.2571 + 0.1714 + 0.4571 + 0.1143 = 1.0000 \ ✓$$

### Why must the four probabilities always add up to exactly 1?

Two reasons:

**Reason 1 — They are disjoint (no overlap).**
A ticket cannot belong to two regions at once. It is impossible for a ticket to be both technical and non-technical. So none of the four boxes share any tickets.

**Reason 2 — They are exhaustive (they cover everything).**
Every single ticket belongs to one of the four boxes. There is no fifth category.

When a group of events is both disjoint and exhaustive, the rule of probability guarantees their probabilities sum to exactly 1. Because 1 represents "certainty" — something must happen, and these four options cover all possibilities.

---

---

# Part 2 — Union Probabilities

## What is a union and why do we need a special formula?

### What does "union" (∪) mean?

$$P(A \cup B) = \text{probability that } A \text{ happens, OR } B \text{ happens, OR both happen}$$

The key word is **"OR"**. A union is satisfied when **at least one** condition is true.

Think of it like a security checkpoint:
- Event A = you have a valid ID
- Event B = you are on the guest list
- A ∪ B = you can enter if you have a valid ID, OR you are on the guest list, OR both

### Why can't we just add P(A) + P(B)?

Because some tickets satisfy **both** conditions at the same time (they are in A AND in B).
If we add P(A) + P(B), those tickets get **counted twice** — once for being in A and once for being in B.

To fix this, we subtract the overlap once:

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

This is called the **Inclusion-Exclusion Principle**.

### There is also a shortcut using the complement:

$$P(A \cup B) = 1 - P(A^c \cap B^c)$$

### Why does this shortcut work?

Because the only tickets that are NOT in A ∪ B are tickets where neither A nor B happened — which is exactly the region Aᶜ ∩ Bᶜ.
Subtracting that region from 1 gives you everything that IS in A ∪ B.

---

## P(T ∪ S) — Technical OR solved on first contact (or both)

### What tickets are included?

This union includes every ticket that meets at least one of these conditions:
- It is a technical ticket (regardless of whether it was solved)
- It was solved on first contact (regardless of whether it was technical)
- It is both technical AND solved

### What tickets are excluded?

Only the tickets that fail BOTH conditions:
- Not technical (non-technical)
- AND not solved on first contact

That is the region Tᶜ ∩ Sᶜ = **40 tickets**.

### Calculation using inclusion-exclusion

We need three values from the table:

- **P(T) = 150/350** → there are 150 technical tickets in total (row total of T)
- **P(S) = 250/350** → there are 250 tickets solved on first contact (column total of S)
- **P(T ∩ S) = 90/350** → there are 90 tickets that are BOTH technical AND solved — this is the overlap that gets double-counted, so we subtract it once

$$P(T \cup S) = \frac{150}{350} + \frac{250}{350} - \frac{90}{350} = \frac{150 + 250 - 90}{350} = \frac{310}{350} \approx \mathbf{0.8857}$$

### Verification using the complement shortcut

The excluded region is Tᶜ ∩ Sᶜ = 40 tickets:

$$1 - P(T^c \cap S^c) = 1 - \frac{40}{350} = 1 - 0.1143 = 0.8857 \ ✓$$

Both methods give the same answer — 0.8857.

### What does 0.8857 mean?

If you pick one random ticket, there is an **88.6% chance** it is either technical, or solved on first contact, or both.
Only 40 out of 350 tickets (11.4%) fail both conditions.

---

## P(Tᶜ ∪ S) — Non-technical OR solved on first contact (or both)

### What tickets are included?

This union includes every ticket that meets at least one of these conditions:
- It is a non-technical ticket (regardless of whether it was solved)
- It was solved on first contact (regardless of whether it was technical)
- It is both non-technical AND solved

### What tickets are excluded?

Only the tickets that fail BOTH conditions:
- Not non-technical (meaning: it IS technical)
- AND not solved on first contact

That is the region T ∩ Sᶜ = **60 tickets**.

### Calculation using inclusion-exclusion

We need three values:

- **P(Tᶜ) = 200/350** → there are 200 non-technical tickets (row total of Tᶜ)
- **P(S) = 250/350** → there are 250 tickets solved on first contact (column total of S)
- **P(Tᶜ ∩ S) = 160/350** → there are 160 tickets that are BOTH non-technical AND solved — the overlap we subtract once

$$P(T^c \cup S) = \frac{200}{350} + \frac{250}{350} - \frac{160}{350} = \frac{200 + 250 - 160}{350} = \frac{290}{350} \approx \mathbf{0.8286}$$

### Verification using the complement shortcut

The excluded region is T ∩ Sᶜ = 60 tickets:

$$1 - P(T \cap S^c) = 1 - \frac{60}{350} = 1 - 0.1714 = 0.8286 \ ✓$$

### What does 0.8286 mean?

If you pick one random ticket, there is an **82.9% chance** it is either non-technical, or solved on first contact, or both.
Only 60 out of 350 tickets (17.1%) fail both conditions — those are the technical tickets that could not be solved on first contact.

---

---

# Part 3 — Conditional Probabilities

## What is conditional probability and why do we use a different formula?

### The idea in plain language

**Normal probability** asks: "Out of all 350 tickets, what fraction is X?"

**Conditional probability** asks: "I already know one fact about the ticket. Given that fact, what fraction is X?"

Knowing extra information **shrinks our world**. Instead of 350 tickets, we now look at a smaller group.

### A simple everyday example

Imagine a bag with 10 balls:
- 6 red balls, 4 blue balls
- 3 of the red balls have a star on them
- 1 of the blue balls has a star on it

Normal: P(star) = 4/10 = 0.4

Conditional: "I already picked a red ball. What is the chance it has a star?"
→ We only look at the 6 red balls. 3 of them have stars.
→ P(star | red) = 3/6 = 0.5

The extra information (it is red) changed our denominator from 10 to 6.

### The formula

$$P(S \mid T) = \frac{P(T \cap S)}{P(T)}$$

**Why this formula?**

- The numerator P(T ∩ S) = tickets that satisfy BOTH conditions (technical AND solved)
- The denominator P(T) = all technical tickets

Dividing one by the other gives the fraction of technical tickets that are also solved.

Notice: the 350s cancel out completely.

$$P(S \mid T) = \frac{90/350}{150/350} = \frac{90}{150}$$

So in practice, the conditional probability is just: how many are in the intersection, divided by how many are in the given condition group.

---

## P(S | T) — Probability of being solved, given the ticket is technical

### Step 1 — Understand what "given T" means

We are told: the ticket IS technical. So we completely ignore the 200 non-technical tickets.
We now work only with the **150 technical tickets** — the top row of the data table.

```
We go from this:               To focusing only on this:
All 350 tickets                The 150 technical tickets (top row)

T:   [ 90 | 60 ] = 150    →   [ 90 | 60 ] = 150
Tᶜ:  [160 | 40 ] = 200        (ignored)
```

### Step 2 — Within those 150 technical tickets, how many were solved?

Look at the top row of the data table:
- Technical AND solved (T ∩ S) = **90**
- Technical AND not solved (T ∩ Sᶜ) = **60**
- Total technical = **150**

Out of 150 technical tickets, 90 were solved on first contact.

### Step 3 — Calculate

$$P(S \mid T) = \frac{90}{150} = \mathbf{0.60}$$

Using the formula with fractions over 350 (same result):

$$P(S \mid T) = \frac{P(T \cap S)}{P(T)} = \frac{90/350}{150/350} = \frac{90}{150} = 0.60$$

### What does 0.60 mean?

Among technical tickets only, **60% are solved on first contact**.
Out of every 10 technical tickets, 6 get resolved immediately, 4 do not.

---

## P(S | Tᶜ) — Probability of being solved, given the ticket is non-technical

### Step 1 — Understand what "given Tᶜ" means

We are told: the ticket is non-technical. So we completely ignore the 150 technical tickets.
We now work only with the **200 non-technical tickets** — the bottom row of the data table.

```
We go from this:               To focusing only on this:
All 350 tickets                The 200 non-technical tickets (bottom row)

T:   [ 90 | 60 ] = 150         (ignored)
Tᶜ:  [160 | 40 ] = 200    →   [160 | 40 ] = 200
```

### Step 2 — Within those 200 non-technical tickets, how many were solved?

Look at the bottom row of the data table:
- Non-technical AND solved (Tᶜ ∩ S) = **160**
- Non-technical AND not solved (Tᶜ ∩ Sᶜ) = **40**
- Total non-technical = **200**

Out of 200 non-technical tickets, 160 were solved on first contact.

### Step 3 — Calculate

$$P(S \mid T^c) = \frac{160}{200} = \mathbf{0.80}$$

Using the formula with fractions over 350 (same result):

$$P(S \mid T^c) = \frac{P(T^c \cap S)}{P(T^c)} = \frac{160/350}{200/350} = \frac{160}{200} = 0.80$$

### What does 0.80 mean?

Among non-technical tickets only, **80% are solved on first contact**.
Out of every 10 non-technical tickets, 8 get resolved immediately, only 2 do not.

---

---

# Part 4 — Does Ticket Type Affect First-Contact Resolution?

## What question are we actually answering?

We want to know: **does knowing whether a ticket is technical give us useful information about whether it will be solved on first contact?**

In mathematical language: are events T and S **independent** or **dependent**?

---

## What does "independent" mean?

Two events are **independent** if knowing one gives you zero information about the other.

> **Example of independent events:** Flipping a coin and rolling a dice. Knowing the coin landed heads tells you nothing about what the dice will show. They do not influence each other.

> **Example of dependent events:** Weather and umbrella sales. Knowing it is raining tells you umbrella sales will be higher. They are connected.

**The mathematical test for independence:**

If T and S are independent, then:
$$P(S \mid T) = P(S \mid T^c) = P(S)$$

All three must be equal. If knowing the ticket type (T or Tᶜ) does not change the probability of being solved (S), then ticket type has no effect.

---

## Apply the test to our data

First, calculate all three values:

**P(S) — overall probability of being solved (ignoring ticket type entirely):**

$$P(S) = \frac{250}{350} \approx 0.7143 \quad (71.4\%)$$

**P(S | T) — probability of being solved, given technical (from Part 3):**

$$P(S \mid T) = \frac{90}{150} = 0.60 \quad (60\%)$$

**P(S | Tᶜ) — probability of being solved, given non-technical (from Part 3):**

$$P(S \mid T^c) = \frac{160}{200} = 0.80 \quad (80\%)$$

---

## Compare the three values

| What we measure | Value | Distance from overall rate |
|---|:---:|:---:|
| P(S) — all tickets | 71.4% | baseline |
| P(S \| T) — technical only | 60.0% | **11.4 points below** |
| P(S \| Tᶜ) — non-technical only | 80.0% | **8.6 points above** |

The gap between the two conditional probabilities is:

$$0.80 - 0.60 = 0.20 \quad \text{(20 percentage points)}$$

---

## What does this tell us?

The three values are **not equal**:

$$P(S \mid T) = 0.60 \neq 0.80 = P(S \mid T^c)$$

This means the test for independence **fails**. T and S are **not independent** — they are **dependent**.

Ticket type absolutely changes the probability of first-contact resolution:
- A technical ticket has only a **60% chance** of being solved on first contact.
- A non-technical ticket has an **80% chance** of being solved on first contact.

---

## Why does this make sense in real life?

Technical problems are inherently more complex. They often involve:
- Software bugs that require developers to write a fix
- Server or network issues that need infrastructure engineers
- Error codes that require reading logs or running diagnostics
- Problems that cannot be reproduced or diagnosed in real time

Non-technical problems are usually procedural and handled with standard steps:
- Resetting a password → done in 2 minutes
- Processing a refund → done by following a checklist
- Updating billing info → done through a standard form

So it is completely logical that technical tickets are solved on first contact less often. The data confirms what common sense already tells us.

---

## Formal conclusion

$$\text{Since } P(S \mid T) \neq P(S \mid T^c), \text{ events T and S are NOT independent.}$$

**Being a technical ticket does change — and specifically lowers — the probability of first-contact resolution.**
Technical tickets are solved on first contact 60% of the time, compared to 80% for non-technical tickets — a gap of 20 percentage points.
