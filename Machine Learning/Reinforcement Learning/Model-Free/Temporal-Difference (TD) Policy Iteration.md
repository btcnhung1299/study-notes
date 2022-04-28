Used in [[Planning without environment description, or model-free planning]] to find optimal [[policy]] by iteratively doing [[Temporal-Difference (TD) Policy Evaluation]] in [[Model-Free Policy Iteration (Model-Free Value-based RL)]].

## Algorithms
 
- [[SARSA]]
- [[Q-learning]]
- [[DQN (Deep Q-Network)]]


---
# FAQ

1. Q: Why is SARSA good for on-policy learning while Q-learning good for [[Off-Policy Learning]]?
	A: Q-learning does not need to follow the behavior policy to pick next action and thus, is useful in off-policy learning.

2. Q: What is the intuition behind target network in DQN?
	A: We do not want to bootstrap towards current network because it is unstable. Hence, we use another network, or target network, that is rarely updated to reduce oscilliation.