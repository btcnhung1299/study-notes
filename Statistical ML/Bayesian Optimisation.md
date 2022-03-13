Bayesian optimisation is a sequential strategy to optimise an unknown function $f$, which is expensive to evaluate. In general, Bayesian optimisation tries to find the next best evaluation point in order to best approximating the maximum $\mathbf{x}^*$ of $f$
$$\mathbf{x}^* = \arg \max_{\mathbf{x} \in \mathcal{X}} f(\mathbf{x})$$

## General Procedure
1. Place an unknown prior distribution over the target function, which is an unknown function.
2. Gather function evaluations and update the prior distribution to form a posterior distribution over.
3. Based on the posterior distribution, the **acquisition function** $\alpha: \mathcal{X} \rightarrow \mathbb{R}$ will pick the point with best score (of *exploration* and *exploitation*) to evaluate next.

Note: Gaussian processes are widely used in Bayesian optimisation for continuous space.

# FAQ
1. *Q: Example of difficult-to-evaluation function?*
	A: Hyperparameter optimisation would be a prime example. Consider a model $f$ with hyperparameters denoted by $x$. To find best hyperparameters, we need to train that specific model on the whole dataset, which is time-consuming.

2. *Q: What are main differences in Bayesian optimisation and gradient-based optimisation?*
	A: Gradient-based optimisation (see [[Optimisation Algorithms]]) relies on derivatives, whereas the target function is unknown for Bayesian optimisation, and thereby no derivatives can be obtained.

3. *Q: Why Bayesian optimisation is said to be "data-efficient"?*
	A: Since it smartly chooses the next point for evaluation, Bayesian optimisation is data-efficient.

4. *Q: What are connections between Bayesian optimisation and [[Reinforcement Learning]]?*
	A: Bayesian optimisation can be seen as multi-arm bandits problem in RL. Particularly, Bayesian optimisation is a sequential decision problem of choosing the next evaluation point where the decisions do not affect the state of the system (the function $f$).