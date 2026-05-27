# Problem 2 — Four Regions of a Sample Space

## Given Information

| Ticket type | Solved (S) | Not solved (Sᶜ) | Total |
|---|---|---|---|
| Technical (T) | 90 | 60 | 150 |
| Non-technical (Tᶜ) | 160 | 40 | 200 |
| **Total** | 250 | 100 | **350** |

> **Key idea:** Each cell count divided by the grand total (350) gives the joint probability for that region.

---

## Part 1 — Probabilities of the Four Disjoint Regions

Each probability is computed as (cell count) ÷ (total tickets = 350):

$$P(T \cap S) = \frac{90}{350} = \frac{9}{35} \approx 0.2571$$

$$P(T \cap S^c) = \frac{60}{350} = \frac{6}{35} \approx 0.1714$$

$$P(T^c \cap S) = \frac{160}{350} = \frac{16}{35} \approx 0.4571$$

$$P(T^c \cap S^c) = \frac{40}{350} = \frac{4}{35} \approx 0.1143$$

**Verification — the four regions must sum to 1:**

$$\frac{9}{35} + \frac{6}{35} + \frac{16}{35} + \frac{4}{35} = \frac{9+6+16+4}{35} = \frac{35}{35} = 1 \checkmark$$

---

## Part 2 — Union Probabilities

**Key rule:** The complement of a union is the intersection of the complements:

$$P(A \cup B) = 1 - P(A^c \cap B^c)$$

### P(T ∪ S)

$T \cup S$ fails only when a ticket is *both* non-technical *and* not solved — i.e. $T^c \cap S^c$.

$$P(T \cup S) = 1 - P(T^c \cap S^c) = 1 - \frac{4}{35} = \frac{31}{35} \approx 0.8857$$

*Check using the four regions directly:*

$$P(T \cup S) = P(T \cap S) + P(T \cap S^c) + P(T^c \cap S) = \frac{9+6+16}{35} = \frac{31}{35} \checkmark$$

### P(Tᶜ ∪ S)

$T^c \cup S$ fails only when a ticket is *both* technical *and* not solved — i.e. $T \cap S^c$.

$$P(T^c \cup S) = 1 - P(T \cap S^c) = 1 - \frac{6}{35} = \frac{29}{35} \approx 0.8286$$

---

## Part 3 — Conditional Probabilities

The conditional probability formula is:

$$P(A \mid B) = \frac{P(A \cap B)}{P(B)}$$

> **Shortcut:** When conditioning on a row (or column) of a table, the totals of 350 cancel — you can read directly from the row totals.

### P(S | T) — resolution rate for technical tickets

$$P(S \mid T) = \frac{P(T \cap S)}{P(T)} = \frac{90/350}{150/350} = \frac{90}{150} = \boxed{0.60}$$

### P(S | Tᶜ) — resolution rate for non-technical tickets

$$P(S \mid T^c) = \frac{P(T^c \cap S)}{P(T^c)} = \frac{160/350}{200/350} = \frac{160}{200} = \boxed{0.80}$$

---

## Part 4 — Does Ticket Type Affect Resolution? (Independence Check)

Two events A and B are **independent** if and only if $P(A \mid B) = P(A)$.

| Probability | Value | Interpretation |
|---|---|---|
| P(S) — overall resolution rate | 250/350 ≈ **0.714** | Baseline |
| P(S \| T) — technical tickets | **0.60** | Below baseline |
| P(S \| Tᶜ) — non-technical tickets | **0.80** | Above baseline |

Since $P(S \mid T) = 0.60 \neq P(S) \approx 0.714$, the events T and S are **not independent**.

**Conclusion:** Yes, ticket type does change the probability of first-contact resolution. Technical tickets are resolved on first contact only 60% of the time, compared to 80% for non-technical tickets and 71.4% overall. Being a technical ticket makes first-contact resolution *less* likely.
