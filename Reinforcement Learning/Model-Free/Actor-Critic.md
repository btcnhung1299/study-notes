Actor-critic combines the idea of [[Policy Gradient (Model-Free Policy-based RL)]] and [[Value Function Approximation]] to simultaneously learn to approximate both optimal [[Policy]] and corresponding [[Action-value Function, or Q-function]].
- Critic: update $\tilde{Q}_{\tilde{\pi}}(s, a \mid w)$
- Actor: update $\tilde{\pi}(a \mid s, \theta)$

The SGD (see [[Policy Gradient (Model-Free Policy-based RL)]] for more information) becomes
$$\theta \leftarrow \theta + \alpha \nabla \log \tilde{\pi}(a \mid s, \theta) \tilde{Q}_{\tilde{\pi}}(s, a \mid w)$$

## Algorithms
- [[DDPG (Deep Deterministic Policy Gradient)]]