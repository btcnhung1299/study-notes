**Marginal probability**:
- $p(X=x)$
- Description: The probability of the event $X=x$, not conditioned on another event (unconditional)
- Example: the probability that a drawn card is red (heart and diamond cards) is $p(\text{red}) = 2/4$

**Joint distribution**:
- $p(X=x,Y=y)$
- Description: The probability of the event $X=x$ and $Y=y$ happening at the same time
- Example: the probability that a drawn card is red and not greater than 10 $p(\text{red}, \leq 10) = \frac{4*10}{52} * \frac{2}{4}$

**Conditional probability**:
- $p(Y=y \mid X=x)$
- Description: The probability of the event $Y=y$ given $X=x$ occured
- Example: the probability that a drawn card is not greater than 10, given it is a red card $p(\leq 10 \mid \text{red}) = \frac{2 * 10}{52 * \frac{2}{4}}$

---
# FAQ

1. Q: What is the relation between marginal, joint, and conditional probability?
A: They relate to each other via **the sum rule** and **the product rule (a.k.a., the chain rule)**:
	- The sum rule states that the marginal of $x$ is obtained by summing (or taking integral) the joint over $y$.
		$$P(x) = \sum_y P(x, y) = \int_{-\infty}^{\infty} P(x, y)dy$$
	- The product rule states that the joint can be decomposed as a product of the marginal and the conditional.
		$$P(x, y) = P(x|y)P(y)$$