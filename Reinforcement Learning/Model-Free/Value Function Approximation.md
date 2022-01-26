### Description
Instead of table lookup, we can use (machine learning) models, parameterized by $\theta$, to apprioximate value function for
- Each state ([[state-value function, or utility]])
	$$\tilde{V}(s, \theta) \approx V_\pi(s)$$
- Each (state, action) pair ([[action-value function, or Q-function]])
	$$\tilde{Q}(s, a, \theta) \approx Q_\pi(s,a)$$
	
### Objective function
Objectively, we minimize the [[Mean Square Error (MSE)]] between approximated value function and the true/oracle value function
$$J(\theta) = \mathbb{E}_\pi[ (V_\pi(s) - \tilde{V}(s, \theta))^2 ]$$

Consequently, weights are updated by
$$\begin{gather}
\theta \leftarrow \theta -\frac{1}{2} \alpha \nabla_\theta J(\theta) \\
\text{where }
\nabla_\theta J(\theta) = -2 \mathbb{E}_\pi \left[ (V_\pi(s) - \tilde{V}(s, \theta) ) \nabla_\theta \tilde{V}(s, \theta) \right] \\
\end{gather}$$

In fact, we do not have the true value function: we can use model-free prediction to create ground-truth labels for value functions from our dataset, which is a supervised learning.

Particularly,
- Use [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]]
$$-\frac{1}{2}\nabla_\theta J(\theta) = \mathbb{E}_\pi \left[ G_t - \tilde{V}(S_t, \theta) \right] \nabla_\theta \tilde{V}(S_t, \theta)$$

- Use [[Temporal-Difference (TD) Policy Evaluation]]
$$-\frac{1}{2}\nabla_\theta J(\theta) = \mathbb{E}_\pi \left[ R_{t+1} + \gamma \tilde{V}(S_{t+1}, \theta) - \tilde{V}(S_t, \theta) \right] \nabla_\theta \tilde{V}(S_t, \theta)$$
> Observation: We do not take derivative of $\tilde{V}(S_{t+1}, \theta)$ because (intuitively), we do want to update the function with respect to the value function of a state we haven't observed its reward.

**Note**: In practice, we use two set of parameters:
- $\theta$: up-to-date parameters to compute $\tilde{V}(S_t, \theta)$
- $\theta^-$: old, fixed parameters to compute $\tilde{V}(S_t, \theta^-)$. In practice, $\theta^-$ is obtained by remained parameters in several steps ago and periodically updated. We do not use the current network because of its short-term oscillations.