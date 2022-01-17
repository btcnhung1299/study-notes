#### Description
Used in [[Planning without environment description, or model-free planning]] to find the optimal [[policy]].

#### Algorithm
**A. Description**
1. Policy Evaluation: use either [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]] or [[Temporal-Difference (TD) Policy Evaluation]] with [[action-value function, or Q-function]] (we cannot use [[state-value function, or utility]] because we do not have the environment model).

	> Observation: We might not cover the whole state space because we iteratively update policy based on our own experience (i.e. not influenced by underlying $P^a_{ss\prime}$). A solution is $\epsilon$-greedy strategy.
	
2. Policy Improvement: do [[ε-greedy Improvement]] to randomly choose between taking greedy actions and exploratory actions.

> The policy iteration is guaranteed to converge to optimal policy if the policy is [[GLIE]].

**B. Variants**
- Monte-Carlo (MC) Policy Iteration
- [[Temporal-Difference (TD) Policy Iteration]]
	
