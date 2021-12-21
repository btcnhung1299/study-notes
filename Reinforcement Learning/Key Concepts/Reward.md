**Description**: Reward function $R$ denotes reward for performing action $a_t$ in state $s_t$ and arriving at the state $s_{t+1}$
$$
\begin{gather}
r_t = R(s_t, a_t, s_{t+1}) = R(s_t, a_t) = R(s_t) \\
R: |\mathcal{S}| \times |\mathcal{A}| \times |\mathcal{S}| \rightarrow \mathbb{R}
\end{gather}
$$

**Return**: is cumulative rewards over a [[Episode (Trajectory)]] $\tau$

- Finite-horizon undiscounted return:
$$R(\tau) = \sum_{t=1}^{T} r_t$$
where $T$ is horizon size.

- Infinite-horizon discounted return:
$$R(\tau) = \sum_{t=1}^{\infty} \gamma^{t} r_t$$
where $\gamma$ is a [[discount factor]].