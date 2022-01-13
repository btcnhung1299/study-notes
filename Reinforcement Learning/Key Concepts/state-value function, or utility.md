#### State-Value Function (Utility)
State-value function is a [[value function]] with respect to current state $S_t = s$ only. Intuitively, it works as a measurement of how good the current state is, particularly in terms of expected [[return]].
$$\begin{align}
V_{\pi}(S_t = s) 
&= \mathbb{E}_{\pi} [G_t \mid S_t = s] \\
&= \mathbb{E}_{\pi} [R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots \mid S_t = s]
\end{align}$$
Note: Next actions are chosen according to policy $\pi$, resulting a corresponding [[return]].

> The [[Bellman equation]] provides the decomposition of current state-value function and the next state-value function, which is useful for dynamic programming.

#### Optimal State-value Function
$$V_{*}(S_t=s) = V_{\pi^*}(S_t=s) = \max_{\pi} V_{\pi}(S_t = s)$$

> The state-value function (and its optimal version) relates to [[action-value function, or Q-function]], more in [[value function]].