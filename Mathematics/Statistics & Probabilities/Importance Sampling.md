Importance sampling is a technique to estimate the expected value of a function $f(X)$ of the distribution of interest using samples from another distribution (namely, sampling/proposal distribution).

## General Flow
Let $P$ be the distribution of interest and $Q$ be the proposal distribution. We can estimate the expected value of $f(X)$ with respect to $P$ using $Q$ by the following transformation
$$\begin{align}
\mathbb{E}_{x \sim P} [f(x)]
&= \int f(x) P(x) \,dx \\
&= \int f(x) \frac{P(x)}{Q(x)} Q(x) \,dx \\
&= \mathbb{E}_{x \sim Q} \left[ f(x) \frac{P(x)}{Q(x)} \right]
\end{align}$$

Intuitively, we can think of importance sampling as giving correcting weights, i.e. $\frac{P(x)}{Q(x)},$ to $f(x)$  where $X$ are sampled from proposal, easier-to-handle distribution $Q$.

> Observation: By $\frac{P(x)}{Q(x)}$, the corresponding value will be less changed if the probability is similar in both distributions.

---

# FAQ
1. Q: Why does it called "Importance sampling"?