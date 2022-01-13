#### Action-value Function (Q-function)
Action-value function is a [[value function]] with respect to current state $S_t = s$ with action taken $A_t = a$. Intuitively, it works as a measurement of how benefit the action is, particularly in terms of expected [[return]].
$$\begin{align}
Q_{\pi}(S_t = s, A_t = a) &= \mathbb{E}_{\pi}[G_t \mid S_t = s, A_t = a] \\
&= \mathbb{E}_{\pi}[R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} +\dots \mid S_t = s, A_t = a] \\
\end{align}$$
Note: Next actions are chosen according to policy $\pi$, resulting a corresponding [[return]].

> The [[Bellman equation]] provides the decomposition of current action-value function and the next action-value function, which is useful for dynamic programming.

#### Optimal Action-value Function
Optimal action-value function is the action-value function corresponding with the best policy $\pi^{*}$ over all policies.
$$Q_{*}(S_t=s, A_t=a) = Q_{\pi^*}(S_t=s, A_t=a) = \max_{\pi} Q_{\pi}(S_t = s, A_t=a)$$

> The action-value function relates to [[state-value function, or utility]], more in [[value function]].
