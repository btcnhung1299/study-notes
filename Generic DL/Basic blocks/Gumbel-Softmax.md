Gumbel distribution
$$z_i = g_i + \log{\pi_i}$$
where $g_i \sim U(0,1)$ and $\pi_i$ is the probability of class $i$.

The Gumbel-Softmax, enhanced with temperature $\tau$, is annealed with definition:
$$\sigma_i = \text{softmax}(z_i / \tau)$$

> Observations: When $\tau$ approaches 0, Gumbel distribution resembles one-hot distribtion. When $\tau$ approaches $\infty$, it looks like uniform.