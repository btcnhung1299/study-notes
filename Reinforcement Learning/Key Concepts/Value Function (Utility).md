**Purpose**: Predict the expected return, or [[reward]]-to-go from the current state $s$ onwards, given actions always chosen by policy $\pi$.

**Formulation**:
$$V^{\pi}(s) = \mathbb{E}_{\tau \sim \pi} \left[ R(\tau) \mid s_0 = s \right]$$
where $R(\tau)$ is return over trajectory $\tau = (s_0, a_0, s_1, a_1, \dots)$.
