#### Description
Value function measures the expected return if you start from a certain state ([[state-value function, or utility]]) or a certain state and action ([[action-value function, or Q-function]])

- In [[state-value function, or utility]], $V(s) = \mathbb{E}[G_t \mid S_t = s]$
- In [[action-value function, or Q-function]], $Q(s,a) = \mathbb{E}[G_t \mid S_t = s, A_t = a]$
where $G_t$ is return at timestep $t$ (see [[reward]])

---

#### FAQ
1. Q: What is the connection between [[state-value function, or utility]] and [[action-value function, or Q-function]]?
A: The state-value function can be obtained from action-value function by marginalizing all possible actions with the probability distribution of each action $\pi(a \mid s)$
$$V(s) = \sum_{a} \pi(a \mid s) Q(s,a)$$
Furthermore, the optimal state-value function can be obtained by following the optimal action decided by action-value function (e.g. in [[Policy Iteration]], [[Value Iteration]]).
$$V_{*}(s) = \max_{a} Q_{*}(s,a)$$