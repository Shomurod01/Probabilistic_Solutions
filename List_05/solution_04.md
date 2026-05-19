## Task 4 — Geometric Distribution
 
### What is it?
Repeat independent trials (each with success probability `p`) until the **first success**. Count the number of trials.
 
- **Sample space:** `Ω = {S, FS, FFS, FFFS, …}`
- **Example outcome:** `ω = FFFS` → failed 3 times, succeeded on trial 4
- **Random variable:** `X(ω)` = trial number of first success → `X(FFFS) = 4`
---
 
### Formulas
 
| | Formula | When to use |
|---|---|---|
| **PMF** | `P(X = k) = (1−p)^(k−1) · p` | Probability of first success on exactly trial k |
| **CDF** | `P(X ≤ k) = 1 − (1−p)^k` | Probability of first success by trial k |
| **Tail** | `P(X > k) = (1−p)^k` | Still no success after k trials |
| **Range** | `P(a ≤ X ≤ b) = (1−p)^(a−1) − (1−p)^b` | First success between trials a and b |
 
**Key stats:** Mean = `1/p` · Variance = `(1−p)/p²` · Mode = `1`
 
---
 
### Support: {1, 2, 3, …}
Starts at 1 (need at least one trial). Infinite because you could theoretically fail forever — every k has positive probability.
 
---
 
### How p affects the shape
 
| p | Mean | Shape |
|---|---|---|
| Large (0.8) | 1.25 | Tall spike at k=1, drops steeply |
| Medium (0.3) | 3.33 | Moderate decay |
| Small (0.1) | 10.0 | Slow decay, long right tail |
 
---
 
### Example Calculations (p = 0.3, k = 4, a = 2, b = 6)
 
```
P(X = 4)      = (0.7)³ · 0.3        = 0.1029  (10.3%)
P(X ≤ 4)      = 1 − (0.7)⁴         = 0.7599  (76.0%)
P(X > 4)      = (0.7)⁴              = 0.2401  (24.0%)
P(2 ≤ X ≤ 6) = (0.7)¹ − (0.7)⁶    = 0.5824  (58.2%)
```
 
---
 
### Memoryless Property
Past failures give **no information** about the future:
```
P(X > m + n | X > m) = P(X > n)
```
If you've already failed 10 times, the odds going forward are exactly the same as at the start.
 
---
 
### Applications
Job applications until first offer · Sales calls until first sale · Network retries · Manufacturing defects · Drug trials · Games
 
---
