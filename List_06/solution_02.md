# Problem 2 — Four regions of a sample space

We have the following contingency table (counts of tickets):

| Ticket type | Solved (S) | Not solved (Sᶜ) | Total |
|-------------|-----------|----------------|-------|
| Technical (T) | 90 | 60 | 150 |
| Non-technical (Tᶜ) | 160 | 40 | 200 |
| Total | 250 | 100 | 350 |

Total number of tickets = 350.

## 1. Probabilities of the four disjoint regions

Each probability = (number of tickets in that region) / (total tickets).

- **P(T ∩ S)** = 90/350 = 9/35  
- **P(T ∩ Sᶜ)** = 60/350 = 6/35  
- **P(Tᶜ ∩ S)** = 160/350 = 16/35  
- **P(Tᶜ ∩ Sᶜ)** = 40/350 = 4/35  

**Check sum:**  
9/35 + 6/35 + 16/35 + 4/35 = 35/35 = 1 ✓

## 2. Compute P(T ∪ S)

**Meaning:** Ticket is technical **or** solved (or both).  
It includes three regions: T∩S, T∩Sᶜ, Tᶜ∩S.

\[
P(T \cup S) = \frac{9}{35} + \frac{6}{35} + \frac{16}{35} = \frac{31}{35}
\]

**Alternative formula (inclusion–exclusion):**  
\[
P(T \cup S) = P(T) + P(S) - P(T \cap S)
\]
\[
P(T) = \frac{150}{350} = \frac{15}{35},\quad P(S) = \frac{250}{350} = \frac{25}{35},\quad P(T \cap S) = \frac{9}{35}
\]
\[
P(T \cup S) = \frac{15}{35} + \frac{25}{35} - \frac{9}{35} = \frac{31}{35} \quad \checkmark
\]

## 3. Compute P(Tᶜ ∪ S)

**Meaning:** Ticket is non‑technical **or** solved.  
Includes: T∩S, Tᶜ∩S, Tᶜ∩Sᶜ.

\[
P(T^c \cup S) = \frac{9}{35} + \frac{16}{35} + \frac{4}{35} = \frac{29}{35}
\]

**Alternative using complement:**  
The complement of (Tᶜ ∪ S) is T ∩ Sᶜ.  
\[
P(T^c \cup S) = 1 - P(T \cap S^c) = 1 - \frac{6}{35} = \frac{29}{35}
\]

## 4. Conditional probabilities

**Definition:**  
\[
P(S \mid T) = \frac{P(S \cap T)}{P(T)} = \frac{90/350}{150/350} = \frac{90}{150} = \frac{3}{5} = 0.6
\]

\[
P(S \mid T^c) = \frac{P(S \cap T^c)}{P(T^c)} = \frac{160/350}{200/350} = \frac{160}{200} = \frac{4}{5} = 0.8
\]

## 5. Does being a technical ticket change the probability of being solved?

Yes, because:  
- \(P(S \mid T) = 0.6\)  
- \(P(S \mid T^c) = 0.8\)  
- Overall \(P(S) = 250/350 \approx 0.714\)

Technical tickets have a **lower** chance (60%) of being solved on first contact compared to non‑technical tickets (80%).  
Thus, the event “technical” does affect the probability of “solved” – they are **not independent**.

---

## Final answers in a table

| Region | Probability |
|--------|-------------|
| P(T ∩ S) | 9/35 |
| P(T ∩ Sᶜ) | 6/35 |
| P(Tᶜ ∩ S) | 16/35 |
| P(Tᶜ ∩ Sᶜ) | 4/35 |

- \(P(T \cup S) = \frac{31}{35}\)  
- \(P(T^c \cup S) = \frac{29}{35}\)  
- \(P(S \mid T) = \frac{3}{5}\)  
- \(P(S \mid T^c) = \frac{4}{5}\)  

Yes, being technical changes the probability (it lowers it).
