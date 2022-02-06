We can apply likelihood ratio to convert a gradient to an expectation.

$$\begin{align}
\nabla_\theta f(x, \theta) &= \frac{\nabla_\theta f(x, \theta)}{f(x, \theta)} f(x, \theta) \\
 &= \underbrace{\nabla_\theta \log f(x, \theta)}_{\text{score function}} f(x, \theta) \tag*{as $(\log a)' = \frac{1}{a} a'$}
\end{align}$$