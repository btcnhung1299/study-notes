Assume that policy can be approximatedly represented as with [[value function]] by [[Value Function Approximation]], we consider the parameteric policy
$$\tilde{\pi}(a \mid s, \theta) \approx \pi_\theta(a \mid s)$$

## Objective Function
A good policy is a policy that gives maximum [[value function]], or expected [[return (cumulative reward)]]. Hence, we define our objective function is to maximize the [[value function]] and use **gradient ascent** to solve.

- In deterministic environment, we can use value function from the initial state $S_t$ or "start value".
	$$J(\theta) = V_\tilde{\pi}(S_1)$$

- In continuous environment where there is no initial state, we consider the expectation over all states.
	$$J(\theta) = \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) V_\tilde{\pi}(s)$$
	where $d_\tilde{\pi}(s)$ is the [[Stationary Distribution of a Markov Chain]] for policy $\tilde{\pi}$.
	
## Policy Gradient
- **Numerically**, we can find $\nabla J(\theta)$ using finite difference as we perturb by $\epsilon$
	$$\frac{\delta J(\theta)}{\delta \theta} = \frac{J(\theta + \epsilon \mu_k) - J(\theta)}{\epsilon}$$
	where $\mu_k$ is a unit vector, i.e. 1 in the k-th component, 0 elsewhere

	> Application: The numerical approach can work with arbitrary policy, even if it is indifferentiable. However, the $\mu_k$ can be arbitrarily large when applied with neural networks (with billion paramaters)

- **Analytically**, we can directly take derivations. The derivation is stated in *Policy Gradient Theorem* as follows (you can find full expansion in [proof](#proof))
	$$\nabla_\theta J(\theta) = \mathbb{E}_{\tilde{\pi}}[ \nabla \log \tilde{\pi}(a \mid s, \theta) Q_\pi(s, a) ]$$

	> Observation: the algorithm that relies on policy can suffer from premature convergence because it lacks exploration (as it solely acts upon the specified policy)


### Proof
- First, we expand the [[state-value function (utility)]] by [[value function]]:
$$\begin{align}
	\nabla_\theta J(\theta) 
	&= \nabla_\theta \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) V_\tilde{\pi}(s) \\
	&= \nabla_\theta \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}} \tilde{\pi}(a \mid s, \theta) Q_\tilde{\pi}(s, a)
	\end{align}$$

- It can be proven that (will come back when I have more time?)
	$$\begin{align}
	\nabla_\theta \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}} \tilde{\pi}(a \mid s, \theta) Q_\tilde{\pi}(s, a) \\ 
	\propto 
	\sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}}  \nabla_\theta \tilde{\pi}(a \mid s, \theta) Q_\tilde{\pi}(s, a)
	\end{align}$$
	
- Using the [[Likelihood Ratio]] trick, we know that the derivative can be represented with a *score function* (a gradient of log-likelihood) as follows
	$$\begin{align}
	\nabla_\theta J(\theta) &\propto 
	\sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}}  \nabla_\theta \tilde{\pi}(a \mid s, \theta) Q_\tilde{\pi}(s, a) \\
	&= \sum_{s \in \mathcal{S}} d_{\tilde{\pi}}(s) 
	\sum_{a \in \mathcal{A}} \overbrace{\tilde{\pi}(a \mid s, \theta) \nabla_\theta \log \tilde{\pi}(a \mid s, \theta)}^{\nabla_\theta \tilde{\pi}(a \mid s, \theta)} Q_\tilde{\pi}(s,a) \\
	&= \mathbb{E}_{\tilde{\pi}}[ \nabla \log \tilde{\pi}(a \mid s, \theta) Q_\pi(s, a) ]
	\end{align}$$
	
## Algorithms

- [[REINFORCE]]

**Reduce Variance Trick**: In practice, we subtract baseline function to reduce the variance of our estimators while keeping the bias unchanged. Baseline function is determined a function of state, denoted as $B(s)$, because
$$\begin{align}
\mathbb{E}_\tilde{\pi} [ \nabla \log \tilde{\pi}(s \mid a, \theta) B(s) ] 
&= \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}} \nabla_{\theta} \tilde{\pi}(a \mid s, \theta) B(s) \\
&= \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) B(s) \nabla_{\theta} \underbrace{\sum_{a \in \mathcal{A}} \tilde{\pi}(a \mid s, \theta)}_{1} \\
&= 0
\end{align}$$

[[state-value function (utility)]] can serve as such baseline, resulting in [[advantage function]].

---
# FAQ
1. Q: In which case policy gradient is preferred over [[Model-Free Policy Iteration (Model-Free Value-based RL)]]?
	A: Policy-based RL is especially helpful for stochastic policy when picking greedy actions in value-based RL requires multiple optimization problems.