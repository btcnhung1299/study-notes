**Description**: Measure how much better a specific action $a$ in state $s$ (measured by [[Q-function]]) over randomly selecting an action according to the policy $\pi$ (measured by [[Utility]]).
$$A^{\pi}(s,a) = Q^{\pi}(s,a) - U^{\pi}(s)$$

*Observation*: The connection between them can be concluded from the above equation:
$$U(s) = \max_{a}Q(s,a)$$
where $Q(s,a)$ is Q-value of doing action $a$ at state $s$.
