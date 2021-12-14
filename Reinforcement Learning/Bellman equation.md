**Definition**: [[Utility]] of a state $s$ is the sum of its immediate reward $R(s)$ and the expected [[Utility]] of its successor states.

**Formulation**: In passive RL, utility given a fixed policy $\pi$ follows:
$$U^{\pi}(s) = R(s) + \gamma \sum_{s^{\prime}} P(s^{\prime} \mid s, a) U^{\pi}(s^{\prime})$$

In active RL, utility is computed under the assumption of [[Optimal policy]], that is:
$$U(s) = R(s) + \gamma \max_{a} \sum_{s^{\prime}} P(s^{\prime} \mid s, a) U(s^{\prime})$$

**Solution**: Either value iteration or policy iteration algorithms