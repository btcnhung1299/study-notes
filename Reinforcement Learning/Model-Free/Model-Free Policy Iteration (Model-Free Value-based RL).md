#### Description
Used in [[Planning without environment description, or model-free planning]] to find the optimal [[Policy]] via estimated [[Value Function]].

#### Algorithm
In [[Planning with given environment description using Dynamic Programming]], we can either use [[Policy Iteration]] or [[Value Iteration]] to do control/planning. However, it is not possible to do [[Value Iteration]] because no model is provided (i.e. we do not know transition probability $P^a_{ss^\prime}$). Hence, we opt to use [[Policy Iteration]] with model-free prediction integrated with several changes.

**A. Description**
1. Policy Evaluation: use either [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]] or [[Temporal-Difference (TD) Policy Evaluation]] with [[Action-value Function, or Q-function]] (we cannot use [[State-value Function, or Utility]] because we do not have the environment model).

	> Observation: We might not cover the whole state space because we iteratively update policy based on our own experience (i.e. not influenced by underlying $P^a_{ss\prime}$). A solution is $\epsilon$-greedy strategy.
	
2. Policy Improvement: do [[Epsilon-greedy Policy Improvement]] to randomly choose between taking greedy actions and exploratory actions.

> The policy iteration is guaranteed to converge to optimal policy if the policy is [[GLIE]].

**B. Variants**
- Monte-Carlo (MC) Policy Iteration
- [[Temporal-Difference (TD) Policy Iteration]]
	
