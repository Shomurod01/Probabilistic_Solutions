## Part 1: Probability of Exactly 3 Requests

Substitute $\lambda = 5$ and $k = 3$:

$$P(X = 3) = \frac{5^3 \cdot e^{-5}}{3!} = \frac{125 \cdot e^{-5}}{6}$$

Since $e^{-5} \approx 0.006738$:

$$P(X = 3) = \frac{125 \cdot 0.006738}{6} = \frac{0.84224}{6} \approx 0.1404 = 14.04\%$$

---

## Part 2: Probability of At Least One Request

"At least one" means $X \geq 1$. It is easiest to use the complement:

$$P(X \geq 1) = 1 - P(X = 0)$$

First calculate $P(X = 0)$:

$$P(X = 0) = \frac{5^0 \cdot e^{-5}}{0!} = e^{-5} \approx 0.006738$$

Therefore:

$$P(X \geq 1) = 1 - 0.006738 \approx 0.9933 = 99.33\%$$
