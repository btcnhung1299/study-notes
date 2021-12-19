Reward $R: |\mathcal{S}| \times |\mathcal{A}| \times |\mathcal{S}| \rightarrow \mathbb{R}$

**Description**: a function of the current state of the world $s_t$, the action just taken $a_t$, and the next state $s_{t+1}$
$$r_t = R(s_t, a_t, s_{t+1}) = R(s_t, a_t) = R(s_t)$$
where $R$ is a reward function of the enviroment.


**Return**: is cumulative rewards, or a function over a [[Trajectory (Episode)]] $\tau$

- Finite-horizon undiscounted return:
$$R(\tau) = \sum_{t=0}^{T} r_t$$
where $T$ is a size of the horizon, or window size.

- Infinite-horizon discounted return:
$$R(\tau) = \sum_{t=0}^{\infty} \gamma^{t} r_t$$
where $\gamma$ is a [[discount factor]].