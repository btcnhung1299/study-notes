**Definition**:
Given two random variables $X$ and $Y$ whose values in $I \in \mathbb{R}$.
Let $F_X(x) = P(X \leq x)$ is the CDF of $X$ and $F_Y(y) = P(Y \leq y)$ is the CDF of $Y$.
- *Identically distributed*: $F_X(a) = F_Y(a), \forall a \in I$
	CDF of the two variables are the same at all points.
- *Independent*: $F_X,Y(x,y) = F_X(x)F_Y(y), \forall x, y \in I$
	The probability of this event doesn't interfere with the another.

---

*Q: How to check the IID assumption on a dataset*:
A:
- Compute the correlation
- Draw lag plots
- Perform turning point tests