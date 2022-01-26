## Description
Used in [[Planning without environment description, or model-free planning]] to find optimal [[policy]] by iteratively doing [[Temporal-Difference (TD) Policy Evaluation]] in [[Model-Free Value-based RL, or Policy Iteration]].

## Algorithms
 
### SARSA

Vanilla algorithm that attempts to directly apply policy iteration:
- Policy Evaluation: directly use [[Temporal-Difference (TD) Policy Evaluation]], i.e.
	$Q_\pi(S_t, A_t) \leftarrow Q_\pi(S_t, A_t) + \alpha(R_{t+1} + \gamma Q_\pi(S_{t+1}, A_{t+1}) - Q_\pi(S_t, A_t))$
	
	> Observation: The update follows S-A-R-S'-A' order, which gives rise to the algorithm's name. Intuitively, we are doing one-step lookahead.

- Policy Improvement: e.g. $\epsilon$-greedy

*Pseudocode*:
![400](../resources/SARSA.png)

**Note**: We can use n-step TD to make the best of [[Temporal-Difference (TD) Policy Evaluation]] and [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]], resulted in n-step SARSA.

### Q-Learning

- Almost similar to SARSA, but considering the optimal next action instead of expectation of all actions **defined by the current policy $\pi$**.
	$Q_\pi(S_t, A_t) \leftarrow Q_\pi(S_t, A_t) + \alpha(R_{t+1} + \gamma \max_{a \in \mathcal{A}} Q_\pi(S_{t+1}, a) - Q_\pi(S_t, A_t))$

- Alternatively, we can see Q-learning as SARSA in a special case when $\pi$ is a greedy policy, i.e. $\pi(s) = \arg \max_{a \in \mathcal{A}} Q(s, a).$
	$$Q(S_{t+1}, \pi(S_{t+1})) 
	= Q(S_{t+1}, \arg \max_{a \in \mathcal{A}} Q(S_{t+1}, a)) 
	= \max_{a \in \mathcal{A}} Q_\pi(S_{t+1}, a)$$

*Pseudocode*:
![400](../resources/Qlearning.png)

> Observation: Picking the optimal action means that it does not need to follow the current policy $\pi$ and the optimal action may not be followed in the next step. Compared to SARSA pseudocode, we indeed have no specific next action update at the end of the inner loop.

#### Deep Q-Network (DQN)

- Basically DQN is Q-learning with Action-[[Value Function Approximation]], enhanced with *experience replay* and *target network*
- In experience replay, all samples (i.e. a tupe of <state, action, next reward>) are pooled to a replay memory. A minibatch of samples are randomly chosen for optimization to break correlation among consecutive samples.
- Target network is used to compute optimal next action, which is soft updated after a specific number of iterations.

---
## FAQ

Q: Why is SARSA good for on-policy learning while Q-learning good for [[Off-Policy Learning]]?
A: Q-learning does not need to follow the behavior policy to pick next action and thus, is useful in off-policy learning.

Q: What is the intuition behind target network in DQN?
A: We do not want to bootstrap towards current network because it is unstable. Hence, we use another network, or target network, that is rarely updated to reduce oscilliation.