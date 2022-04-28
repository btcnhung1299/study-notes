## State-Value Function

State-value function, or utility, is a [[value function]] with respect to current state $S_t = s$. Intuitively, it measures how good the current state is, particularly in terms of expected [[return (cumulative reward)]], no matter what actions to be taken.
$$\begin{align}
V_{\pi}(S_t = s) 
&= \mathbb{E}_{\pi} [G_t \mid S_t = s] \\
&= \mathbb{E}_{\pi} [R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots \mid S_t = s]
\end{align}$$

## Optimal State-value Function
$$V_{*}(S_t=s) = V_{\pi^*}(S_t=s) = \max_{\pi} V_{\pi}(S_t = s)$$

> The state-value function (and its optimal version) relates to [[action-value function (Q-function)]], more in [[value function]].