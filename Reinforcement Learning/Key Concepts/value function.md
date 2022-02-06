## Value Function

Value function measures the expected return given the current information. Based on the type of initial information, value function is formulated as

- [[State-value Function, or Utility]], $V(s) = \mathbb{E}[G_t \mid S_t = s]$
- [[Action-value Function, or Q-function]], $Q(s,a) = \mathbb{E}[G_t \mid S_t = s, A_t = a]$

where $G_t$ is [[Return as cumulative onward reward]] at timestep $t$.

## Connection between value functions

- The state-value function can be obtained from action-value function by marginalizing all possible actions with the probability distribution of each action $\pi(a \mid s)$
$$V(s) = \sum_{a} \pi(a \mid s) Q(s,a)$$

- On the other hand, the optimal state-value function can be obtained by following the optimal action decided by action-value function (e.g. in [[Policy Iteration]], [[Value Iteration]]).
$$V_{*}(s) = \max_{a} Q_{*}(s,a)$$