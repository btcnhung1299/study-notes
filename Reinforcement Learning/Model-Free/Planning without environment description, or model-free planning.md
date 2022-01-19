#### Description
We want to plan our policy $\pi$ such that it is optimal in the environment, which we have no information about the [[Markov Decision Process]] behind it. At the same time, the optimal policy must satisfy the Bellman Optimality Equation (see [[Bellman equation]]).

#### Approaches
> Observation: With known [[Markov Decision Process]], we can either use [[Policy Iteration]] or [[Value Iteration]] to do control/planning. However, it is not possible to do [[Value Iteration]] because no model is provided (i.e. we do not know transition probability $P^a_{ss^\prime}$). Hence, we opt to use [[Policy Iteration]] with model-free prediction integrated with several changes.

[[Model-Free Policy Iteration]]:
1. Monte-Carlo (MC) Policy Iteration
2. [[Temporal-Difference (TD) Policy Iteration]]
3. [[Eligibility Traces]]