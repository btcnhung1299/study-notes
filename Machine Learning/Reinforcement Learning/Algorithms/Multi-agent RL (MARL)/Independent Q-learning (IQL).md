Each agent learns separate [[value function]] with global goal of optimising joint Q and chooses optimal actions based on learnt (individual) Q.

## Flow
Agent $a$ seeks optimal action-value function (i.e. action-value function with respect to the optimal policy) $Q_a^*$ whose value conditioned on its own observations such that they jointly optimise global $Q^*$.

$$Q^*(s, u_a | \pi_{-a}) = \sum_{\mathbf{u}_a} \pi_{-a}(-\mathbf{u}_a |s) \left[ r + \gamma \sum P(s^\prime | s, u_a, -\mathbf{u}_a) \max_{u^\prime_a} Q^*_a(s^\prime, u^\prime_a) \right]$$

## Components
Each agent can act differently because they receive different observations.

## Extension
**Independent actor-critic** uses essentially the same idea of separate functions for agents just like in IQL but with actor-critic framework. 