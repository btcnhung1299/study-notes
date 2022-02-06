Discount factor is used to prefer immediate rewards than future rewards.

Discount factor is typically included in [[Return as cumulative onward reward]], resulted in discounted return (infinite version):
$$\sum_{t=0}^{\infty} \gamma^t r_{t+1} \tag{1}$$
where $r_t = R(s_t, a_t)$ is a reward.

**Mathematical properties**:
- Force equation (1) to be converged to a finite value.