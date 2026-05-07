# Problem 4 — Building Complex Statements from Simple Ones

---

## First — Understand the Setup

Before we do anything, let us understand what we are working with.

We roll **two dice**. The first die gives us row **i**, the second die gives us column **j**.

Every cell in this grid is one possible outcome:

```
      j=1  j=2  j=3  j=4  j=5  j=6
i=1    .    .    .    .    .    .
i=2    .    .    .    .    .    .
i=3    .    .    .    .    .    .
i=4    .    .    .    .    .    .
i=5    .    .    .    .    .    .
i=6    .    .    .    .    .    .
```

There are **6 × 6 = 36** total outcomes. Our job is to find which cells belong to each event.

---

## Part A — Basic Events

---

### Event A: The sum equals 7

**Step 1 — What does sum = 7 mean?**

It means we need i + j = 7. For every value of i, we ask what value of j gives exactly 7.

**Step 2 — Go through every row one by one:**

```
i = 1 → j must be 6 → because 1 + 6 = 7 ✅
i = 2 → j must be 5 → because 2 + 5 = 7 ✅
i = 3 → j must be 4 → because 3 + 4 = 7 ✅
i = 4 → j must be 3 → because 4 + 3 = 7 ✅
i = 5 → j must be 2 → because 5 + 2 = 7 ✅
i = 6 → j must be 1 → because 6 + 1 = 7 ✅
```

**Step 3 — Check that all other pairs do NOT sum to 7:**

```
(1,1) → 1+1=2 ❌
(1,2) → 1+2=3 ❌
(1,3) → 1+3=4 ❌
(1,4) → 1+4=5 ❌
(1,5) → 1+5=6 ❌
(1,6) → 1+6=7 ✅ ← only this one in row 1
```

Repeat this thinking for every row. Only one cell per row qualifies.

**Step 4 — Mark the grid:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X     ← 1+6=7
i=2       .    .    .    .    X    .     ← 2+5=7
i=3       .    .    .    X    .    .     ← 3+4=7
i=4       .    .    X    .    .    .     ← 4+3=7
i=5       .    X    .    .    .    .     ← 5+2=7
i=6       X    .    .    .    .    .     ← 6+1=7
```

**Step 5 — Count and verify:**

We have exactly **6 outcomes** in Event A. Each row contributes exactly one X
moving one step to the left each time — forming a diagonal.

---

### Event B: First die is greater than second (i > j)

**Step 1 — What does i > j mean?**

For each cell (i, j) we ask: is the row number strictly greater than the column number?

**Step 2 — Go through every cell one by one:**

```
Row i=1:
  (1,1) → 1 > 1? NO  .
  (1,2) → 1 > 2? NO  .
  (1,3) → 1 > 3? NO  .
  (1,4) → 1 > 4? NO  .
  (1,5) → 1 > 5? NO  .
  (1,6) → 1 > 6? NO  .
  → No X in row 1

Row i=2:
  (2,1) → 2 > 1? YES X
  (2,2) → 2 > 2? NO  .
  (2,3) → 2 > 3? NO  .
  (2,4) → 2 > 4? NO  .
  (2,5) → 2 > 5? NO  .
  (2,6) → 2 > 6? NO  .
  → One X in row 2

Row i=3:
  (3,1) → 3 > 1? YES X
  (3,2) → 3 > 2? YES X
  (3,3) → 3 > 3? NO  .
  (3,4) → 3 > 4? NO  .
  (3,5) → 3 > 5? NO  .
  (3,6) → 3 > 6? NO  .
  → Two X in row 3

Row i=4:
  (4,1) → 4 > 1? YES X
  (4,2) → 4 > 2? YES X
  (4,3) → 4 > 3? YES X
  (4,4) → 4 > 4? NO  .
  (4,5) → 4 > 5? NO  .
  (4,6) → 4 > 6? NO  .
  → Three X in row 4

Row i=5:
  (5,1) → 5 > 1? YES X
  (5,2) → 5 > 2? YES X
  (5,3) → 5 > 3? YES X
  (5,4) → 5 > 4? YES X
  (5,5) → 5 > 5? NO  .
  (5,6) → 5 > 6? NO  .
  → Four X in row 5

Row i=6:
  (6,1) → 6 > 1? YES X
  (6,2) → 6 > 2? YES X
  (6,3) → 6 > 3? YES X
  (6,4) → 6 > 4? YES X
  (6,5) → 6 > 5? YES X
  (6,6) → 6 > 6? NO  .
  → Five X in row 6
```

**Step 3 — Mark the grid:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    .    ← nothing (1 is never > j)
i=2       X    .    .    .    .    .    ← only j=1
i=3       X    X    .    .    .    .    ← j=1,2
i=4       X    X    X    .    .    .    ← j=1,2,3
i=5       X    X    X    X    .    .    ← j=1,2,3,4
i=6       X    X    X    X    X    .    ← j=1,2,3,4,5
```

**Step 4 — Count and verify:**

```
Row 1 → 0 outcomes
Row 2 → 1 outcome
Row 3 → 2 outcomes
Row 4 → 3 outcomes
Row 5 → 4 outcomes
Row 6 → 5 outcomes
Total → 0+1+2+3+4+5 = 15 outcomes
```

The X marks form a **lower-left triangle**.

---

### Event C: At least one die shows 6

**Step 1 — What does at least one die shows 6 mean?**

It means i = 6 OR j = 6 OR both. We split this into three groups:

```
Group 1: first die = 6  → entire row 6
Group 2: second die = 6 → entire column 6
Group 3: both = 6       → cell (6,6) already counted in both groups
```

**Step 2 — Find all cells in row 6:**

```
(6,1) → i=6 ✅
(6,2) → i=6 ✅
(6,3) → i=6 ✅
(6,4) → i=6 ✅
(6,5) → i=6 ✅
(6,6) → i=6 ✅
```

**Step 3 — Find all cells in column 6:**

```
(1,6) → j=6 ✅
(2,6) → j=6 ✅
(3,6) → j=6 ✅
(4,6) → j=6 ✅
(5,6) → j=6 ✅
(6,6) → j=6 ✅ (already counted above)
```

**Step 4 — Mark the grid:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X    ← j=6
i=2       .    .    .    .    .    X    ← j=6
i=3       .    .    .    .    .    X    ← j=6
i=4       .    .    .    .    .    X    ← j=6
i=5       .    .    .    .    .    X    ← j=6
i=6       X    X    X    X    X    X    ← i=6 (entire row)
```

**Step 5 — Count and verify:**

```
Column 6 contributes     → 6 cells
Row 6 contributes        → 6 cells
Cell (6,6) counted twice → subtract 1
Total = 6 + 6 - 1       = 11 outcomes
```

---

## Part B — Compound Events

### How compound events work

Before starting here are the three rules we will use over and over:

```
A ∪ B  (OR)  → X if the cell is in A OR in B or BOTH
A ∩ B  (AND) → X if the cell is in BOTH A and B
Ā      (NOT) → flip every X to . and every . to X
```

We will always compare grids side by side so you can see exactly where each X comes from.

---

### Statement 1 — A ∪ C (Sum is 7 OR at least one die shows 6)

**Step 1 — Write out Event A and Event C side by side:**

```
Event A:                         Event C:
   j=1 j=2 j=3 j=4 j=5 j=6        j=1 j=2 j=3 j=4 j=5 j=6
i=1  .   .   .   .   .   X      i=1  .   .   .   .   .   X
i=2  .   .   .   .   X   .      i=2  .   .   .   .   .   X
i=3  .   .   .   X   .   .      i=3  .   .   .   .   .   X
i=4  .   .   X   .   .   .      i=4  .   .   .   .   .   X
i=5  .   X   .   .   .   .      i=5  .   .   .   .   .   X
i=6  X   .   .   .   .   .      i=6  X   X   X   X   X   X
```

**Step 2 — For every cell ask: is it X in A OR X in C?**

```
(1,1) → A=.  C=.  → . (in neither)
(1,6) → A=X  C=X  → X (in both)
(2,5) → A=X  C=.  → X (only in A)
(2,6) → A=.  C=X  → X (only in C)
(6,1) → A=X  C=X  → X (in both)
(6,2) → A=.  C=X  → X (only in C)
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X
i=2       .    .    .    .    X    X
i=3       .    .    .    X    .    X
i=4       .    .    X    .    .    X
i=5       .    X    .    .    .    X
i=6       X    X    X    X    X    X
```

**Step 4 — Count:**

```
From A only     → (2,5)(3,4)(4,3)(5,2) = 4 outcomes
From C only     → column 6 rows 2-5 and row 6 cols 2-5 = 8 outcomes
In both A and C → (1,6)(6,1) = 2 outcomes
Total           → 4 + 8 + 2 = 15 outcomes ✅
```

---

### Statement 2 — A ∩ C (Sum is 7 AND at least one die shows 6)

**Step 1 — Write out Event A and Event C side by side (same grids as above)**

**Step 2 — For every X in Event A check if it is also X in Event C:**

```
(1,6) → A=X  C=X  → X ✅ (sum=7 AND has a 6)
(2,5) → A=X  C=.  → . ❌ (sum=7 but no 6)
(3,4) → A=X  C=.  → . ❌ (sum=7 but no 6)
(4,3) → A=X  C=.  → . ❌ (sum=7 but no 6)
(5,2) → A=X  C=.  → . ❌ (sum=7 but no 6)
(6,1) → A=X  C=X  → X ✅ (sum=7 AND has a 6)
```

Only two cells pass both conditions.

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X    ← 1+6=7 and j=6 ✅
i=2       .    .    .    .    .    .
i=3       .    .    .    .    .    .
i=4       .    .    .    .    .    .
i=5       .    .    .    .    .    .
i=6       X    .    .    .    .    .    ← 6+1=7 and i=6 ✅
```

**Step 4 — Count: only 2 outcomes**

---

### Statement 3 — B ∩ C (First die greater than second AND at least one die shows 6)

**Step 1 — Write out Event B and Event C side by side:**

```
Event B:                         Event C:
   j=1 j=2 j=3 j=4 j=5 j=6        j=1 j=2 j=3 j=4 j=5 j=6
i=1  .   .   .   .   .   .      i=1  .   .   .   .   .   X
i=2  X   .   .   .   .   .      i=2  .   .   .   .   .   X
i=3  X   X   .   .   .   .      i=3  .   .   .   .   .   X
i=4  X   X   X   .   .   .      i=4  .   .   .   .   .   X
i=5  X   X   X   X   .   .      i=5  .   .   .   .   .   X
i=6  X   X   X   X   X   .      i=6  X   X   X   X   X   X
```

**Step 2 — Check column 6 against B:**

```
(1,6) → B=.  C=X  → . ❌ (1 is not > 6)
(2,6) → B=.  C=X  → . ❌ (2 is not > 6)
(3,6) → B=.  C=X  → . ❌ (3 is not > 6)
(4,6) → B=.  C=X  → . ❌ (4 is not > 6)
(5,6) → B=.  C=X  → . ❌ (5 is not > 6)
(6,6) → B=.  C=X  → . ❌ (6 is not > 6, equal not greater)
```

**Step 3 — Check row 6 against B:**

```
(6,1) → B=X  C=X  → X ✅ (6 > 1 and i=6)
(6,2) → B=X  C=X  → X ✅ (6 > 2 and i=6)
(6,3) → B=X  C=X  → X ✅ (6 > 3 and i=6)
(6,4) → B=X  C=X  → X ✅ (6 > 4 and i=6)
(6,5) → B=X  C=X  → X ✅ (6 > 5 and i=6)
(6,6) → B=.  C=X  → . ❌ (already checked above)
```

**Step 4 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    .
i=2       .    .    .    .    .    .
i=3       .    .    .    .    .    .
i=4       .    .    .    .    .    .
i=5       .    .    .    .    .    .
i=6       X    X    X    X    X    .
```

**Step 5 — Count: 5 outcomes**

---

### Statement 4 — A ∩ B̄ (Sum is 7 BUT first die is NOT greater than second)

**Step 1 — What does B̄ mean?**

```
B̄ means NOT B → we keep cells where i is NOT greater than j
In other words we keep cells where i ≤ j
```

**Step 2 — Take every X in Event A and check if i ≤ j:**

```
(1,6) → i=1  j=6  → 1 ≤ 6? YES ✅ keep
(2,5) → i=2  j=5  → 2 ≤ 5? YES ✅ keep
(3,4) → i=3  j=4  → 3 ≤ 4? YES ✅ keep
(4,3) → i=4  j=3  → 4 ≤ 3? NO  ❌ remove
(5,2) → i=5  j=2  → 5 ≤ 2? NO  ❌ remove
(6,1) → i=6  j=1  → 6 ≤ 1? NO  ❌ remove
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X    ← 1 ≤ 6 ✅
i=2       .    .    .    .    X    .    ← 2 ≤ 5 ✅
i=3       .    .    .    X    .    .    ← 3 ≤ 4 ✅
i=4       .    .    .    .    .    .    ← 4 ≤ 3? NO
i=5       .    .    .    .    .    .    ← 5 ≤ 2? NO
i=6       .    .    .    .    .    .    ← 6 ≤ 1? NO
```

**Step 4 — Count: 3 outcomes**

---

### Statement 5 — A ∩ C̄ (Sum is 7 AND no die shows 6)

**Step 1 — What does C̄ mean?**

```
C̄ means NOT C → we keep cells where neither die shows 6
In other words i ≠ 6 AND j ≠ 6
```

**Step 2 — Take every X in Event A and check if it contains a 6:**

```
(1,6) → j=6 → contains 6 ❌ remove
(2,5) → no 6 anywhere ✅ keep
(3,4) → no 6 anywhere ✅ keep
(4,3) → no 6 anywhere ✅ keep
(5,2) → no 6 anywhere ✅ keep
(6,1) → i=6 → contains 6 ❌ remove
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    .    ← (1,6) removed
i=2       .    .    .    .    X    .    ← no 6 ✅
i=3       .    .    .    X    .    .    ← no 6 ✅
i=4       .    .    X    .    .    .    ← no 6 ✅
i=5       .    X    .    .    .    .    ← no 6 ✅
i=6       .    .    .    .    .    .    ← (6,1) removed
```

**Step 4 — Count: 4 outcomes**

---

### Statement 6 — C ∩ Ā (At least one die shows 6 BUT sum is not 7)

**Step 1 — What does Ā mean?**

```
Ā means NOT A → we keep cells where the sum is NOT 7
```

**Step 2 — Take every X in Event C and remove those where sum = 7:**

```
From column 6:
(1,6) → 1+6=7 ❌ remove
(2,6) → 2+6=8 ✅ keep
(3,6) → 3+6=9 ✅ keep
(4,6) → 4+6=10 ✅ keep
(5,6) → 5+6=11 ✅ keep
(6,6) → 6+6=12 ✅ keep

From row 6:
(6,1) → 6+1=7 ❌ remove
(6,2) → 6+2=8 ✅ keep
(6,3) → 6+3=9 ✅ keep
(6,4) → 6+4=10 ✅ keep
(6,5) → 6+5=11 ✅ keep
(6,6) → already counted above
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    .    ← (1,6) removed (sum=7)
i=2       .    .    .    .    .    X
i=3       .    .    .    .    .    X
i=4       .    .    .    .    .    X
i=5       .    .    .    .    .    X
i=6       .    X    X    X    X    X    ← (6,1) removed (sum=7)
```

**Step 4 — Count: 9 outcomes**

---

### Statement 7 — Ā ∩ B (Sum is NOT 7 AND first die is greater than second)

**Step 1 — Start with Event B and remove cells where sum = 7**

From Event A we know sum = 7 happens at: (4,3), (5,2), (6,1)
These are the only cells in B that also have sum = 7.

**Step 2 — Check every X in B:**

```
(2,1) → 2+1=3  ✅ keep
(3,1) → 3+1=4  ✅ keep
(3,2) → 3+2=5  ✅ keep
(4,1) → 4+1=5  ✅ keep
(4,2) → 4+2=6  ✅ keep
(4,3) → 4+3=7  ❌ remove
(5,1) → 5+1=6  ✅ keep
(5,2) → 5+2=7  ❌ remove
(5,3) → 5+3=8  ✅ keep
(5,4) → 5+4=9  ✅ keep
(6,1) → 6+1=7  ❌ remove
(6,2) → 6+2=8  ✅ keep
(6,3) → 6+3=9  ✅ keep
(6,4) → 6+4=10 ✅ keep
(6,5) → 6+5=11 ✅ keep
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    .
i=2       X    .    .    .    .    .
i=3       X    X    .    .    .    .
i=4       X    X    .    .    .    .    ← (4,3) removed
i=5       X    .    X    X    .    .    ← (5,2) removed
i=6       .    X    X    X    X    .    ← (6,1) removed
```

**Step 4 — Count: 12 outcomes**

---

### Statement 8 — B̄ ∩ C (First die NOT greater than second AND at least one die shows 6)

**Step 1 — What does B̄ mean here?**

```
B̄ means i ≤ j (first die is less than or equal to second die)
```

**Step 2 — Take every X in Event C and check if i ≤ j:**

```
From column 6 (j=6):
(1,6) → 1 ≤ 6? YES ✅ keep
(2,6) → 2 ≤ 6? YES ✅ keep
(3,6) → 3 ≤ 6? YES ✅ keep
(4,6) → 4 ≤ 6? YES ✅ keep
(5,6) → 5 ≤ 6? YES ✅ keep
(6,6) → 6 ≤ 6? YES ✅ keep (equal counts as not greater)

From row 6 (i=6):
(6,1) → 6 ≤ 1? NO  ❌ remove
(6,2) → 6 ≤ 2? NO  ❌ remove
(6,3) → 6 ≤ 3? NO  ❌ remove
(6,4) → 6 ≤ 4? NO  ❌ remove
(6,5) → 6 ≤ 5? NO  ❌ remove
(6,6) → already counted above
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X
i=2       .    .    .    .    .    X
i=3       .    .    .    .    .    X
i=4       .    .    .    .    .    X
i=5       .    .    .    .    .    X
i=6       .    .    .    .    .    X    ← only (6,6) survives from row 6
```

**Step 4 — Count: 6 outcomes**

---

### Statement 9 — (A ∪ C)̄ — NOT (sum is 7 OR at least one die shows 6)

**Step 1 — First recall A ∪ C from Statement 1:**

```
A ∪ C:
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X
i=2       .    .    .    .    X    X
i=3       .    .    .    X    .    X
i=4       .    .    X    .    .    X
i=5       .    X    .    .    .    X
i=6       X    X    X    X    X    X
```

**Step 2 — Flip every single cell. X becomes . and . becomes X:**

```
(1,1) → was . → now X
(1,2) → was . → now X
(1,3) → was . → now X
(1,4) → was . → now X
(1,5) → was . → now X
(1,6) → was X → now .
... and so on for all 36 cells
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       X    X    X    X    X    .
i=2       X    X    X    X    .    .
i=3       X    X    X    .    X    .
i=4       X    X    .    X    X    .
i=5       X    .    X    X    X    .
i=6       .    .    .    .    .    .
```

**Step 4 — Count: 36 - 15 = 21 outcomes**

---

### Statement 10 — (A ∩ C)̄ — NOT (sum is 7 AND at least one die shows 6)

**Step 1 — First recall A ∩ C from Statement 2:**

```
A ∩ C:
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       .    .    .    .    .    X
i=2       .    .    .    .    .    .
i=3       .    .    .    .    .    .
i=4       .    .    .    .    .    .
i=5       .    .    .    .    .    .
i=6       X    .    .    .    .    .
```

**Step 2 — Flip every single cell. X becomes . and . becomes X:**

```
(1,6) → was X → now .
(6,1) → was X → now .
All other 34 cells → were . → now X
```

**Step 3 — Mark the result:**

```
         j=1  j=2  j=3  j=4  j=5  j=6
i=1       X    X    X    X    X    .
i=2       X    X    X    X    X    X
i=3       X    X    X    X    X    X
i=4       X    X    X    X    X    X
i=5       X    X    X    X    X    X
i=6       .    X    X    X    X    X
```

**Step 4 — Count: 36 - 2 = 34 outcomes**

---

## Quick Reference Summary

| Statement | Operation | Plain meaning |
|-----------|-----------|---------------|
| 1 | A ∪ C | in A or C or both |
| 2 | A ∩ C | in both A and C |
| 3 | B ∩ C | in both B and C |
| 4 | A ∩ B̄ | in A but not in B |
| 5 | A ∩ C̄ | in A but not in C |
| 6 | C ∩ Ā | in C but not in A |
| 7 | Ā ∩ B | in B but not in A |
| 8 | B̄ ∩ C | in C but not in B |
| 9 | (A ∪ C)̄ | outside both A and C |
| 10 | (A ∩ C)̄ | not simultaneously in A and C |
