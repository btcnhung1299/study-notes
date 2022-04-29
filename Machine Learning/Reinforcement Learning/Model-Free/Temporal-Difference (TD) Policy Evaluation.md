#### Description
Given a policy, we want to **predict** [[value function]] while having no information about the [[Markov Decision Process (MDP)]] behind the environment.

#### Algorithm
**A. Description**
- Instead of using real feedbacks of return at each state in [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]], we can use *bootstrapping*, i.e. replace exact values with approximation.
	$$\tilde{G}_t = R_{t+1} + \gamma \tilde{V}(S_{t+1})$$
	where $\tilde{V}(S_{t+1})$ is our **current estimation** of value function at next state.
- We have the online implementation formulation with step size $\alpha$ as follows
	$$V(S_t) \leftarrow V(S_t) + \alpha( \tilde{G}_t - V(S_t) )$$
	or
	$$V(S_t) \leftarrow V(S_t) + \alpha \underbrace{(R_{t+1} + \gamma V(S_{t+1}) - V(S_t))}_\text{TD error}$$

> Observation: We don't need to see complete episodes as we replace the true return with our estimation. Therefore, it is compatible with infinite process and offline learning.

**Note**: For [[value function]], we use the following formular:
$$Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha(R_{t+1} + \gamma Q(S_{t+1}, A_{t+1}) - Q(S_t, A_t))$$

> Application: In [[Model-Free Policy Iteration (Model-Free Value-based RL)]], we will take greedy actions with respect to [[value function]] instead of [[state-value function (utility)]] because we do not have $P^a_{ss^\prime}$.

**B. Pseudocode**
![380](TDPrediction.png)

*Note*: Another way to do TD is [[Q-learning]].



---
#### FAQ

Q: How does mean evolve in [[Temporal-Difference (TD) Policy Evaluation]] and [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]]?
A:
- In MC, the mean converges to the true value that minimizes MSE, or best fit to observed return.
- In TD, the mean converges to the true value that best explains the data, or maximize likelihood Markov model (implicitly build Markov process).

![350](MeanEvolvementMCTDPrediction.png)

Q: How is the efficiency of TD compared to [[Adaptive Dynamic Programming (ADP)]]?
A: As shown in [0], TD requires more trials to learn optimal policy. Yet, it requires less computation per observation.