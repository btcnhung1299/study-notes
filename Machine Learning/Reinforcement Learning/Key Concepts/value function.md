## 0. Value function
Value function measures the expected [[return (cumulative reward)]] of the current point, i.e. state (correspond to state-value function) or <state, action> (correspond to action-value function).

## 1. State-value function
State-value function is a value function with respect to current state $S_t = s$. Intuitively, it measures how good the current state is, no matter what actions are taken.
$$\begin{align}
V_{\pi}(S_t = s) 
&= \mathbb{E}_{\pi} [G_t \mid S_t = s] \\
&= \mathbb{E}_{\pi} [R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots \mid S_t = s]
\end{align}$$

## 2. Action-value function
Action-value function is a value function with respect to current state $S_t = s$ in case action $A_t = a$ is taken, intuitively measures how benefit an action is given the current state.
$$\begin{align}
Q_{\pi}(S_t = s, A_t = a) &= \mathbb{E}_{\pi}[G_t \mid S_t = s, A_t = a] \\
&= \mathbb{E}_{\pi}[R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} +\dots \mid S_t = s, A_t = a] \\
\end{align}$$

## 3. Optimal value function
Optimal value function is value function obtained by following the optimal policy $\pi^*$, which yields highest return.
- Optimal state-value function:
$$V_{*}(S_t=s) = V_{\pi^*}(S_t=s) = \max_{\pi} V_{\pi}(S_t = s)$$
- Optimal action-value function:
$$Q_{*}(S_t=s, A_t=a) = Q_{\pi^*}(S_t=s, A_t=a) = \max_{\pi} Q_{\pi}(S_t = s, A_t=a)$$

## 4. Connection between state-value and action-value function
State values can be obtained from action values by marginalizing all possible actions defined by [[policy]] $\pi$
$$V(s) = \sum_{a} \pi(a \mid s) Q(s,a)$$

On the other hand, the optimal state value can be obtained by taking the action that yields maximum action-value, assuming you will follow optimal policy onwards.
$$V_{*}(s) = \max_{a} Q_{*}(s,a)$$


%% Similarly, the optimal state-value function can be obtained by following the optimal action decided by action-value function (e.g. in [[Policy Iteration]], [[Value Iteration]]).
