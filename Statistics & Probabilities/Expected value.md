$$\mathbb{E}[X+Y] = \mathbb{E}[X] + \mathbb{E}[Y]$$

Jensen's inequality:
$$f(\mathbb{E}[X]) \leq \mathbb{E}[f(X)]$$

Minkowski inequality:
$$\left( \mathbb{E}|X+Y|^p \right)^{1/p} \leq \left( \mathbb{E}|X|^p \right)^{1/p} + \left( \mathbb{E}|	Y|^p \right)^{1/p}$$

Variance is the expectation of squared discrepancy
$$\begin{align}
\text{Var}(X) 
&= \boxed{\mathbb{E}[(X - \mu)^2]} \\
&= \mathbb{E}[(X - \mathbb{E}[X])^2] \\
&= \mathbb{E}[X^2 - 2X\mathbb{E}[X] + \mathbb{E}[X]^2] \\ &= \mathbb{E}[X^2] - 2\mathbb{E}[X]\mathbb{E}[X] + \mathbb{E}[X]^2 \\
&= \boxed{\mathbb{E}[X^2] - \mathbb{E}[X]^2}
\end{align}$$