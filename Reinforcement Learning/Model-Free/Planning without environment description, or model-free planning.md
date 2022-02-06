#### Description
We want to plan our policy $\pi$ such that it is optimal in the environment, which we have no information about the [[Markov Decision Process]] behind it. At the same time, the optimal policy must satisfy the Bellman Optimality Equation (see [[Bellman Equation]]).

#### Approaches

In general,

[[Model-Free Policy Iteration (Model-Free Value-based RL)]] | [[Policy Gradient (Model-Free Policy-based RL)]] | [[Actor-Critic]]
- | - | -
Learn value function | No value function | Learn value function
No explicit policy | Learn policy | Learn policy

Particularly,
1. [[Model-Free Policy Iteration (Model-Free Value-based RL)]]:
	- Monte-Carlo (MC) Policy Iteration
	- [[Temporal-Difference (TD) Policy Iteration]]: SARSA, Q-learning, DQN
2. [[Policy Gradient (Model-Free Policy-based RL)]]
3. [[Actor-Critic]]