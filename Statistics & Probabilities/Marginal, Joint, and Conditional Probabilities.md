**Marginal probability**:
- $p(X=x)$
- Description: The probability of the event $X=x$, not conditioned on another event (unconditional)
- E.g., the probability that a drawn card is red (heart and diamond cards) is $p(\text{red}) = 2/4$

**Joint probability**:
- $p(X=x,Y=y)$
- Description: The probability of the event $X=x$ and $Y=y$ happening at the same time
- E.g., the probability that a drawn card is red and not greater than 10 $p(\text{red}, \leq 10) = \frac{4*10}{52} * \frac{2}{4}$

**Conditional probability**:
- $p(Y=y \mid X=x)$
- Description: The probability of the event $Y=y$ given $X=x$ occured
- E.g., the probability that a drawn card is not greater than 10, given it is a red card $p(\leq 10 \mid \text{red}) = \frac{2 * 10}{52 * \frac{2}{4}}$

*Relations between marginal, joint, and conditional probabilities*:
$$P(A|B)*P(B) = P(A,B)$$

**Bayesian theorem**:
$$P(A|B)*P(B) = P(B|A)*P(A)$$

---

*Q: Marginal probability and joint probability?*
A: Marginal probability can be computed from joint probability
$$P(X=x) = \int_y P(X=x, Y=y)$$