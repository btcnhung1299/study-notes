**Reward**: is a function of a single state and action.
$$r_t = R(s_t, a_t)$$
where $R$ is a reward function of the enviroment.

**Return**: is cumulative rewards, or a function over a trajectory $\tau = (s_0, a_0, s_1, a_1, \dots)$

- Finite-horizon undiscounted return:
$$R(\tau) = \sum_{t=0}^{T} r_t$$
where $T$ is a size of the horizon, or window size.

- Infinite-horizon discounted return:
$$R(\tau) = \sum_{t=0}^{\infty} \gamma^{t} r_t$$
where $\gamma$ is a [[discount factor]].