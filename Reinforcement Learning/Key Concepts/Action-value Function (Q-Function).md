**Purpose**: Measure the *value* of a state when arbitrary action $a$ is taken.
*In other words*, Q-function acts as a **value-action function**, or action-utility.

**Formulation**: The Q-function is defined to be the expected return, or reward-to-go (see [[Reward]]), from state $s$ onwards, **taking action $a$, and then follow the policy $\pi$**.
$$Q^{\pi}(s,a) = \mathbb{E}_{\tau \sim \pi} \left[ R(\tau) \mid s_0 = s, a_0 = a \right]$$
where $R(\tau)$ is return over [[Episode (Trajectory)]] $\tau$.