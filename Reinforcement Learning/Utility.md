**Purpose**: Measure the *value* of a state -> judge how good a policy $\pi$ is.
*In other words*, utility acts as a **value function**.

**Formulation**: The utility is defined to be the expected return, or reward-to-go (see [[Reward]]), from state $s$ onwards and **always follow the policy $\pi$**:
$$U^{\pi}(s) = \mathbb{E}_{\tau \sim \pi} \left[ R(\tau) \mid s_0 = s \right]$$
where $R(\tau)$ is return over trajectory $\tau = (s_0, a_0, s_1, a_1, \dots)$.
