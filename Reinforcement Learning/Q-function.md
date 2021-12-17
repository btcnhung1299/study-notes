**Purpose**: Measure the *value* of a state when arbitrary action $a$ is taken.
*In other words*, Q-function acts as a **value-action function**.

**Formulation**: The Q-function is defined to be the expected return, or reward-to-go (see [[Reward, Return]]), from state $s$ onwards, **taking action $a$, and then follow the policy $\pi$**.
$$Q^{\pi}(s,a) = \mathbb{E}_{\tau \sim \pi} \left[ R(\tau) \mid s_0 = s, a_0 = a \right]$$
where $R(\tau)$ is return over trajectory $\tau = (s_0, a_0, s_1, a_1, \dots)$.

*Q: The relation between value [[Q-function]] and [[Utility]]?*
A: The utility (value function) can be obtained from Q-function (value-action function) by:
$$U(s) = \max_{a}Q(s,a)$$
where $Q(s,a)$ is Q-value of doing action $a$ at state $s$.