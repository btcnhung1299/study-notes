#### Description
We want to plan our policy $\pi$ such that it is optimal in the environment, which we have no information about the [[Markov Decision Process]] behind it. At the same time, the optimal policy must satisfy the Bellman Optimality Equation (see [[Bellman equation]]).

#### Approaches

In general,

[[Model-Free Value-based RL, or Policy Iteration]] | [[Model-Free Policy-based RL, or Policy Gradient]] | [[Actor-Critic]]
- | - | -
Learn value function | No value function | Learn value function
No explicit policy | Learn policy | Learn policy

Particularly,
1. [[Model-Free Value-based RL, or Policy Iteration]]:
	- Monte-Carlo (MC) Policy Iteration
	- [[Temporal-Difference (TD) Policy Iteration]]: SARSA, Q-learning, DQN
2. [[Model-Free Policy-based RL, or Policy Gradient]]
3. [[Actor-Critic]]