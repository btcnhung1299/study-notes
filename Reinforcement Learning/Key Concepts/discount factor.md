Discount factor is frequently employed in discounted [[return (cumulative reward)]] to prefer immediate rewards over future rewards.

- The infinite discounted return
$$\sum_{t=0}^{\infty} \gamma^t r_{t+1} \tag{1}$$
where $r_{t+1} = R(S_t=s, A_t=a)$ is reward obtained by taking action $a$ at current state $s$.

The use of discounted return is favourable because:
- It forces equation (1) to be converged to a finite value.
- It reflects our intuition to put more weights on near results, which are more predictable.