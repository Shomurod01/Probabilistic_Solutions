# Problem 2 — Four Regions of a Sample Space

### 🔧 Technical ticket (T)

A ticket is **technical** if the problem involves software, hardware, systems, or anything that requires technical expertise to solve.

| ✅ Technical ticket examples | ❌ Non-technical ticket examples |
|---|---|
| "The server is down" | "I want to cancel my subscription" |
| "I get error code 404" | "Can I get a refund?" |
| "My app won't install" | "How do I update my billing info?" |

> In our dataset: **150 tickets** are technical, **200 tickets** are non-technical.

---

### ✅ Solved during first contact (S)

**First contact** means the very first interaction between the customer and the support agent.

- If the agent solves the problem **in that one call/chat** → ✅ Solved on first contact
- If the problem needs **follow-up, escalation, or more investigation** → ❌ Not solved on first contact

> **Example:**
>
> 🟢 Customer calls → agent resets the password → problem solved immediately → **first contact ✓**
>
> 🔴 Customer calls → agent says "we need to investigate, we'll email you" → **not first contact ✗**

> In our dataset: **250 tickets** were solved on first contact, **100 were not**.

---

## 📋 Data Table

| Ticket type | S (solved 1st contact) | Sᶜ (not solved 1st contact) | Total |
|---|:---:|:---:|:---:|
| T (technical) | 90 | 60 | 150 |
| Tᶜ (non-technical) | 160 | 40 | 200 |
| **Total** | **250** | **100** | **350** |

> **Every probability = count ÷ 350** (total tickets)

---

## 🗺️ The Four Regions — Visualized

Think of it like a 2×2 table of possibilities. Every single ticket falls into exactly one of these four boxes:

```
                    S (solved)          Sᶜ (not solved)
              ┌─────────────────┬──────────────────┐
  T           │   T ∩ S         │   T ∩ Sᶜ         │
  (technical) │   90 tickets    │   60 tickets      │
              ├─────────────────┼──────────────────┤
  Tᶜ          │   Tᶜ ∩ S        │   Tᶜ ∩ Sᶜ        │
  (non-tech)  │   160 tickets   │   40 tickets      │
              └─────────────────┴──────────────────┘
```

- **Top-left:** Technical AND solved → 90 tickets
- **Top-right:** Technical AND NOT solved → 60 tickets
- **Bottom-left:** Non-technical AND solved → 160 tickets
- **Bottom-right:** Non-technical AND NOT solved → 40 tickets

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

### Summary

| Region | Meaning | Count | Probability |
|---|---|:---:|:---:|
| P(T ∩ S) | technical & solved | 90 | **0.2571** |
| P(T ∩ Sᶜ) | technical & not solved | 60 | **0.1714** |
| P(Tᶜ ∩ S) | non-technical & solved | 160 | **0.4571** |
| P(Tᶜ ∩ Sᶜ) | non-technical & not solved | 40 | **0.1143** |

### ✔️ Verification

$$0.2571 + 0.1714 + 0.4571 + 0.1143 = \mathbf{1.0000} \ ✓$$

The four regions are **disjoint** (no overlap) and cover the **entire sample space**, so they must sum to 1.

---

## Part 2 — Union Probabilities

**What does "union" (∪) mean?**

> P(A ∪ B) = probability that **at least one** of A or B happens.
> "A OR B (or both)"

**Formula (inclusion-exclusion):**

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

We subtract the intersection because it gets counted twice otherwise.

**Shortcut using complement:**

$$P(A \cup B) = 1 - P(A^c \cap B^c)$$

---

### P(T ∪ S) — technical OR solved (or both)

$$P(T \cup S) = \frac{150}{350} + \frac{250}{350} - \frac{90}{350} = \frac{310}{350} \approx \mathbf{0.8857}$$

Check using complement:

$$1 - P(T^c \cap S^c) = 1 - 0.1143 = 0.8857 \ ✓$$

> The only tickets **excluded** are non-technical AND not solved — just 40 out of 350.

---

### P(Tᶜ ∪ S) — non-technical OR solved (or both)

$$P(T^c \cup S) = \frac{200}{350} + \frac{250}{350} - \frac{160}{350} = \frac{290}{350} \approx \mathbf{0.8286}$$

Check using complement:

$$1 - P(T \cap S^c) = 1 - 0.1714 = 0.8286 \ ✓$$

> The only tickets **excluded** are technical AND not solved — just 60 out of 350.

---

## Part 3 — Conditional Probabilities

**What does "conditional probability" mean?**

> P(S | T) = "Given that we already know the ticket is technical, what is the probability it was solved?"

**The key idea:** we **zoom in** to just one group, and calculate within that group.

> 🔍 Instead of looking at all 350 tickets, we only look at the **150 technical tickets**.
> Out of those 150, how many were solved? → **90**

**Formula:**

$$P(S \mid T) = \frac{P(T \cap S)}{P(T)} = \frac{\text{tickets that are technical AND solved}}{\text{all technical tickets}}$$

---

### P(S | T) — solved, given technical ticket

$$P(S \mid T) = \frac{90/350}{150/350} = \frac{90}{150} = \mathbf{0.60}$$

> Out of every 10 technical tickets, **6 are solved** on first contact.

---

### P(S | Tᶜ) — solved, given non-technical ticket

$$P(S \mid T^c) = \frac{160/350}{200/350} = \frac{160}{200} = \mathbf{0.80}$$

> Out of every 10 non-technical tickets, **8 are solved** on first contact.

---

## Part 4 — Does Ticket Type Affect First-Contact Resolution?

**Yes — being a technical ticket significantly lowers the probability of first-contact resolution.**

If ticket type had **no effect**, we would expect:

$$P(S \mid T) = P(S \mid T^c) = P(S) \quad \text{(all equal)}$$

But we found:

| Group | First-contact resolution rate |
|---|:---:|
| Technical tickets | **60%** |
| Non-technical tickets | **80%** |
| All tickets — P(S) | **71.4%** |

The gap is **20 percentage points**.

**Why does this make sense intuitively?**

Technical problems (server errors, software bugs) often require investigation, specialist knowledge, or multiple steps — so they're harder to solve in a single interaction. Non-technical problems (billing, account info) are usually straightforward and quick to resolve.

**Formal conclusion:**

Since P(S | T) ≠ P(S | Tᶜ), the events T and S are **not independent**.  
Ticket type **does** change the probability of first-contact resolution.
