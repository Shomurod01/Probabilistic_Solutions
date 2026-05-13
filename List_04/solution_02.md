# Problem 2 — Die × Die

## Overview

When two dice are rolled, every result is a pair **(first die, second die)**.  
The grid below maps all possible outcomes — rows = first die, columns = second die.

**Total outcomes = 6 × 6 = 36**

```
        Second die →
        1   2   3   4   5   6
      ┌───────────────────────
  1   │  .   .   .   .   .   .
F 2   │  .   .   .   .   .   .
i 3   │  .   .   .   .   .   .
r 4   │  .   .   .   .   .   .
s 5   │  .   .   .   .   .   .
t 6   │  .   .   .   .   .   .
```

---

## Part A — Marking Events

### Event 1 — The sum equals 8

**How to find it:** For each value of the first die, calculate what the second die must be (8 minus first). Keep only pairs where the second die is between 1 and 6.

| First die | Second die needed | Valid? |
|:---------:|:-----------------:|:------:|
| 1 | 7 | ✗ impossible |
| 2 | 6 | ✓ |
| 3 | 5 | ✓ |
| 4 | 4 | ✓ |
| 5 | 3 | ✓ |
| 6 | 2 | ✓ |

**Outcomes (5 total):** `(2,6)` `(3,5)` `(4,4)` `(5,3)` `(6,2)`

```
        1   2   3   4   5   6
  1     .   .   .   .   .   .
  2     .   .   .   .   .   X
  3     .   .   .   .   X   .
  4     .   .   .   X   .   .
  5     .   .   X   .   .   .
  6     .   X   .   .   .   .
```

---

### Event 2 — The first die is greater than the second

**How to find it:** Go row by row. For each first-die value `r`, mark every column `c` where `c < r`. This creates a triangle below the main diagonal.

| First die | Second die values that qualify |
|:---------:|:------------------------------:|
| 1 | none |
| 2 | 1 |
| 3 | 1, 2 |
| 4 | 1, 2, 3 |
| 5 | 1, 2, 3, 4 |
| 6 | 1, 2, 3, 4, 5 |

**Outcomes (15 total):** 0 + 1 + 2 + 3 + 4 + 5 = 15

```
        1   2   3   4   5   6
  1     .   .   .   .   .   .
  2     X   .   .   .   .   .
  3     X   X   .   .   .   .
  4     X   X   X   .   .   .
  5     X   X   X   X   .   .
  6     X   X   X   X   X   .
```

---

### Event 3 — Both dice show even numbers

**How to find it:** Even faces on a die are `{2, 4, 6}`. Both dice must independently land on one of these three values — forming a 3×3 block inside the grid.

- Even rows: 2, 4, 6 → **3 choices**
- Even columns: 2, 4, 6 → **3 choices**
- Total: 3 × 3 = **9 outcomes**

```
        1   2   3   4   5   6
  1     .   .   .   .   .   .
  2     .   X   .   X   .   X
  3     .   .   .   .   .   .
  4     .   X   .   X   .   X
  5     .   .   .   .   .   .
  6     .   X   .   X   .   X
```

---

### Event 4 — At least one die shows 6

**How to find it:** "At least one 6" means the first die is 6, **or** the second die is 6, **or** both. This covers the entire last row plus the entire last column.

> **Counting tip (inclusion-exclusion):**  
> Last row (6 outcomes) + Last column (6 outcomes) − overlap at (6,6) counted twice = **11 outcomes**

```
        1   2   3   4   5   6
  1     .   .   .   .   .   X
  2     .   .   .   .   .   X
  3     .   .   .   .   .   X
  4     .   .   .   .   .   X
  5     .   .   .   .   .   X
  6     X   X   X   X   X   X
```

---

### Event 5 — Exactly one die shows 1

**How to find it:** "Exactly one 1" means one die is 1 and the **other is not 1**. Include the first row and first column, but exclude `(1,1)` because that has *two* 1s.

| Group | Outcomes | Count |
|:------|:---------|:-----:|
| First die = 1, second ≠ 1 | `(1,2)` `(1,3)` `(1,4)` `(1,5)` `(1,6)` | 5 |
| Second die = 1, first ≠ 1 | `(2,1)` `(3,1)` `(4,1)` `(5,1)` `(6,1)` | 5 |
| **Total** | | **10** |

```
        1   2   3   4   5   6
  1     .   X   X   X   X   X
  2     X   .   .   .   .   .
  3     X   .   .   .   .   .
  4     X   .   .   .   .   .
  5     X   .   .   .   .   .
  6     X   .   .   .   .   .
```

> Note: `(1,1)` is **not** marked — that would be two 1s, not exactly one.

---

## Part B — Interpreting Marked Grids

### Case 1

```
        1   2   3   4   5   6
  1     .   .   .   .   .   .
  2     .   .   .   .   .   .
  3     .   .   X   X   X   X
  4     .   .   X   X   X   X
  5     .   .   X   X   X   X
  6     .   .   X   X   X   X
```

**Event: Both dice show at least 3**

**Step-by-step reasoning:**

1. Marked rows are 3, 4, 5, 6 → first die shows 3, 4, 5, or 6 → first die ≥ 3
2. Marked columns are 3, 4, 5, 6 → second die shows 3, 4, 5, or 6 → second die ≥ 3
3. Both conditions must hold simultaneously → **"both dice ≥ 3"**
4. Count: 4 rows × 4 columns = **16 outcomes**

---

### Case 2

```
        1   2   3   4   5   6
  1     X   .   .   .   .   .
  2     .   X   .   .   .   .
  3     .   .   X   .   .   .
  4     .   .   .   X   .   .
  5     .   .   .   .   X   .
  6     .   .   .   .   .   X
```

**Event: Both dice show the same number (doubles)**

**Step-by-step reasoning:**

1. Marked outcomes: `(1,1)` `(2,2)` `(3,3)` `(4,4)` `(5,5)` `(6,6)`
2. In every marked pair, the row number equals the column number → first die = second die
3. These lie exactly on the **main diagonal** of the grid
4. The event is **"both dice show equal values"** — also called rolling doubles
5. Count: **6 outcomes** (one per face value)

---

## Summary Table

| Event | Description | Outcome Count | Probability |
|:------|:------------|:-------------:|:-----------:|
| A1 | Sum = 8 | 5 | 5/36 ≈ 0.139 |
| A2 | First die > second die | 15 | 15/36 ≈ 0.417 |
| A3 | Both dice even | 9 | 9/36 = 1/4 |
| A4 | At least one 6 | 11 | 11/36 ≈ 0.306 |
| A5 | Exactly one 1 | 10 | 10/36 ≈ 0.278 |
| B1 | Both dice ≥ 3 | 16 | 16/36 = 4/9 |
| B2 | Both dice equal (doubles) | 6 | 6/36 = 1/6 |

> **Probability formula:** P(event) = number of favourable outcomes ÷ 36
