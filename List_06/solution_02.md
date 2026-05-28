# Problem 2 — Four Regions of a Sample Space

## Data Table

| Ticket type | S (solved 1st contact) | Sᶜ (not solved) | Total |
|---|---|---|---|
| T (technical) | 90 | 60 | 150 |
| Tᶜ (non-technical) | 160 | 40 | 200 |
| **Total** | **250** | **100** | **350** |

> Every probability = count ÷ 350

---

## Part 1 — The Four Region Probabilities

**Step 1 — P(T ∩ S):** technical AND solved on first contact

$$P(T \cap S) = \frac{90}{350} \approx 0.2571$$

**Step 2 — P(T ∩ Sᶜ):** technical AND NOT solved on first contact

$$P(T \cap S^c) = \frac{60}{350} \approx 0.1714$$

**Step 3 — P(Tᶜ ∩ S):** non-technical AND solved on first contact

$$P(T^c \cap S) = \frac{160}{350} \approx 0.4571$$

**Step 4 — P(Tᶜ ∩ Sᶜ):** non-technical AND NOT solved on first contact

$$P(T^c \cap S^c) = \frac{40}{350} \approx 0.1143$$

### Summary Table

| Region | Meaning | Count | Probability |
|---|---|---|---|
| P(T ∩ S) | technical & solved | 90 | **0.2571** |
| P(T ∩ Sᶜ) | technical & not solved | 60 | **0.1714** |
| P(Tᶜ ∩ S) | non-technical & solved | 160 | **0.4571** |
| P(Tᶜ ∩ Sᶜ) | non-technical & not solved | 40 | **0.1143** |

### Verification

$$P(T \cap S) + P(T \cap S^c) + P(T^c \cap S) + P(T^c \cap S^c)$$
$$= 0.2571 + 0.1714 + 0.4571 + 0.1143 = \mathbf{1.0000} \ ✓$$

The four regions are **disjoint** (no overlap) and cover the **entire sample space**, so they must sum to 1.

---

## Part 2 — Union Probabilities

**Key rule (inclusion-exclusion):**

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

**Shortcut using complements:**

$$P(A \cup B) = 1 - P(A^c \cap B^c)$$

### P(T ∪ S) — technical OR solved (or both)

Using inclusion-exclusion:

$$P(T \cup S) = P(T) + P(S) - P(T \cap S) = \frac{150}{350} + \frac{250}{350} - \frac{90}{350} = \frac{310}{350} \approx \mathbf{0.8857}$$

Check using complement:

$$1 - P(T^c \cap S^c) = 1 - 0.1143 = 0.8857 \ ✓$$

### P(Tᶜ ∪ S) — non-technical OR solved (or both)

Using inclusion-exclusion:

$$P(T^c \cup S) = P(T^c) + P(S) - P(T^c \cap S) = \frac{200}{350} + \frac{250}{350} - \frac{160}{350} = \frac{290}{350} \approx \mathbf{0.8286}$$

Check using complement:

$$1 - P(T \cap S^c) = 1 - 0.1714 = 0.8286 \ ✓$$

---

## Part 3 — Conditional Probabilities

**Formula:**

$$P(S \mid A) = \frac{P(A \cap S)}{P(A)}$$

This means: *restrict to the subgroup A, then find what fraction of it is S.*

### P(S | T) — probability of being solved, given technical ticket

$$P(S \mid T) = \frac{P(T \cap S)}{P(T)} = \frac{90/350}{150/350} = \frac{90}{150} = \mathbf{0.60}$$

> Directly: 90 out of 150 technical tickets were solved → **60%**

### P(S | Tᶜ) — probability of being solved, given non-technical ticket

$$P(S \mid T^c) = \frac{P(T^c \cap S)}{P(T^c)} = \frac{160/350}{200/350} = \frac{160}{200} = \mathbf{0.80}$$

> Directly: 160 out of 200 non-technical tickets were solved → **80%**

---

## Part 4 — Does Ticket Type Affect First-Contact Resolution?

**Yes — being a technical ticket significantly lowers the probability of first-contact resolution.**

If ticket type had no effect on resolution, we would expect:

$$P(S \mid T) = P(S \mid T^c) = P(S)$$

But we found:

| Group | P(S \| group) |
|---|---|
| Technical tickets | **0.60** (60%) |
| Non-technical tickets | **0.80** (80%) |
| All tickets — P(S) | 250/350 ≈ **0.714** (71.4%) |

The gap is **20 percentage points**. Technical tickets fall 11 points below the overall rate, while non-technical tickets sit 9 points above it.

**Conclusion:** Since P(S | T) ≠ P(S | Tᶜ), the events T and S are **not independent**. Ticket type does change the probability of first-contact resolution — technical tickets are harder to resolve in a single contact.
