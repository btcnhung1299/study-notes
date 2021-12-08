**Introduction**: Bayesian optimisation is a sequential strategy to optimise difficult-to-evaluate function, typically black-box function.

**Background**: Find global optimiser of an unknown objective function $f$ that takes parameter $\mathbf{x}$. Note that despite $f$ remains unknown, we can evaluate $f(\mathbf{x})$ (e.g., in finding the best hyperparameters).
$$\mathbf{x}^* = \arg \max_{\mathbf{x} \in \mathcal{X}} f(\mathbf{x})$$

**Procedure**:
1. Place an unknown prior distribution over the target function, which is an unknown function.
2. Gather function evaluations and update the prior distribution to form a posterior distribution over.
3. Based on the posterior distribution, the acquisition function $\alpha: \mathcal{X} \rightarrow \mathbb{R}$ will pick the point with best score (of *exploration* and *exploitation*) to evaluate next.

---
*Q: The relation between Bayesian optimisation and gradient-based optimisation?*
A: Gradient-based optimisation (see [[Optimisation Algorithms]]) relies on derivatives, whereas in Bayesian optimisation the target function is unknown and hence no derivatives can be obtained.

*Q: Why Bayesian optimisation is said to be "data efficient"?*
