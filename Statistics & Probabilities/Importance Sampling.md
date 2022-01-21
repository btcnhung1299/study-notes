Importance sampling is a technique to estimate the expectattion of a distribution using samples from another distribution.

Let $P$ is our given distributuon and $Q$ is the target distribution. We can estimate the expection with respect to $Q$ using $P$ as follows
$$\begin{align}
\mathbb{E}_{x \sim P} [f(X)]
&= \sum f(X) P(X) \\
&= \sum f(X) \frac{P(X)}{Q(X)} Q(X) \\
&= \mathbb{E}_{x \sim Q} \left[ f(X)  \frac{P(X)}{Q(X)} \right]
\end{align}$$

Alternatively, we can think of importance sampling as giving correcting weight to current value $f(X)$. The weight $\frac{P(X)}{Q(X)}$ means that the corresponding value will be less changed if the probability is similar in both distributions.

---
### FAQ
Q: Why does it called "Importance sampling"?