**Purpose**: Learning the [[Utility]] $U$

**Idea**: Compare newly-observed utility $R(s) + \gamma U^{\pi}(s^{\prime})$ (when we get the sucessor state $s^{\prime}$) to the current utility $U^{\pi}(s)$ to get the sense of the should-be utility, or *equilibrium* - solution of [[Bellman equation]], for update.

**Formulation**:
$$U^{\pi}(s) \leftarrow U^{\pi}(s) + \alpha \left[ R(s) + \gamma U^{\pi}(s^{\prime}) - U^{\pi}(s)\right]$$
where $\alpha$ is learning rate.

**Note**:
- $a$ is chosen as a function of number of visited state to ensure convergence to the correct value, i.e. $a(n) = \frac{60}{59 + n}$ [0]

---
*Q: How is the efficiency of TD compared to [[Adaptive Dynamic Programming (ADP)]]?*
A: As shown in [0], TD requires more trials to learn optimal policy. Yet, it requires less computation per observation.

---
*References*:
[0] Artificial Intelligence: A Modern Approach