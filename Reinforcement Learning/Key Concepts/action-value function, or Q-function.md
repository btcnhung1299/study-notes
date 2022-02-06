## Action-value Function (Q-function)

Action-value function is a [[Value Function]] with respect to current state $S_t = s$ with action taken $A_t = a$. Intuitively, it measures how benefit the action is, particularly in terms of expected [[Return as cumulative onward reward]], given the current state.
$$\begin{align}
Q_{\pi}(S_t = s, A_t = a) &= \mathbb{E}_{\pi}[G_t \mid S_t = s, A_t = a] \\
&= \mathbb{E}_{\pi}[R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} +\dots \mid S_t = s, A_t = a] \\
\end{align}$$

## Optimal Action-value Function

Optimal action-value function is the action-value function obtained by the best policy $\pi^{*}$ over all policies.
$$Q_{*}(S_t=s, A_t=a) = Q_{\pi^*}(S_t=s, A_t=a) = \max_{\pi} Q_{\pi}(S_t = s, A_t=a)$$
