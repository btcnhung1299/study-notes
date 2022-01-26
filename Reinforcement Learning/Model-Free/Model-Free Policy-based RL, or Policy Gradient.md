## Description
We can directly find the optimal [[policy]] using the same idea in [[Value Function Approximation]] by considering
$$\tilde{\pi}(a \mid s, \theta) \approx \pi_\theta(a \mid s)$$

> Application: Policy-based RL is especially helpful for stochastic policy when picking greedy actions require multiple optimization problems.

## Policy Objective Function
A good policy is a policy with highest [[value function]], or expected [[return]]. Hence, we define our objective function is to maximize the [[value function]] and use **gradient ascent** to solve.

- In deterministic environment, we can use value function from the initial state $S_t$ or "start value".
	$$J(\theta) = V_\tilde{\pi}(S_1)$$

- In continuous environment where there is no initial state, we consider the expectation over all states.
	$$J(\theta) = \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) V_\tilde{\pi}(s)$$
	where $d_\tilde{\pi}(s)$ is the [[stationary distribution of a Markov Chain]] for policy $\tilde{\pi}$.
	
## Policy Gradient
- **Numerically**, we can find $\nabla J(\theta)$ using finite difference as we perturb by $\epsilon$
	$$\frac{\delta J(\theta)}{\delta \theta} = \frac{J(\theta + \epsilon \mu_k) - J(\theta)}{\epsilon}$$
	where $\mu_k$ is a unit vector, i.e. 1 in the k-th component, 0 elsewhere

	> Application: The numerical approach can work with arbitrary policy, even if it is indifferentiable. However, the $\mu_k$ can be arbitrarily large when applied with neural networks (with billion paramaters)

- **Analytically**, we can directly take derivations. The derivation is stated in *Policy Gradient Theorem* as follows (you can find full expansion in [proof](#proof))
	$$\nabla_\theta J(\theta) = \mathbb{E}_{\tilde{\pi}}[ \nabla \log \tilde{\pi}(a \mid s, \theta) Q_\pi(s, a) ]$$
	
### Proof
- First, we expand the [[state-value function, or utility]] by [[action-value function, or Q-function]]:
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

**Reduce Variance Trick**: In practice, we subtract baseline function to reduce the variance of our estimators while keeping the bias unchanged. Baseline function is determined a function of state, denoted as $B(s)$, because
$$\begin{align}
\mathbb{E}_\tilde{\pi} [ \nabla \log \tilde{\pi}(s \mid a, \theta) B(s) ] 
&= \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) \sum_{a \in \mathcal{A}} \nabla_{\theta} \tilde{\pi}(a \mid s, \theta) B(s) \\
&= \sum_{s \in \mathcal{S}} d_\tilde{\pi}(s) B(s) \nabla_{\theta} \underbrace{\sum_{a \in \mathcal{A}} \tilde{\pi}(a \mid s, \theta)}_{1} \\
&= 0
\end{align}$$

[[State-value function, or utility]] can serve as such baseline, resulting in [[Advantage Function]].

### REINFORCE, or Monte-Carlo Policy Gradient
- Use [[return]] $G_t$ achieved via Monte-Carlo method as an unbiased sample of $Q_\pi(s,a)$. 
- Hence, a SGD update becomes
	$$\theta \leftarrow \theta + \alpha \nabla \log \tilde{\pi}(a \mid s, \theta) G_t$$

### Actor-Critic
- Besides learned policy, we also use a "critic" to learn to approximate the [[value function]].
	- Critic: update $\tilde{Q}_{\tilde{\pi}}(s, a \mid w)$
	- Actor: update $\tilde{\pi}(a \mid s, \theta)$
- Hence, a SGD update becomes
	$$\theta \leftarrow \theta + \alpha \nabla \log \tilde{\pi}(a \mid s, \theta) \tilde{Q}_{\tilde{\pi}}(s, a \mid w)$$

### A2C/A3C