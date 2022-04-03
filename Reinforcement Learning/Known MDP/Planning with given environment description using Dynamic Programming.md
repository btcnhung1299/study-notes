#### Description
We are given the **complete description** of the environment, or the [[Markov Decision Process (MDP)]]. We want to plan our policy $\pi$ such that it is optimal in the given environment, i.e. satisfies the Bellman Optimality Equation (see [[Bellman equation]]).

#### Approaches
1. Iteratively approach the optimal policy by [[Policy Iteration]] with auxiliary prediction step via [[Policy Evaluation]]
2. Iteratively approach the optimal value function by [[Value Iteration]]. The optimal policy can be obtained by taking greedy actions on that value function.