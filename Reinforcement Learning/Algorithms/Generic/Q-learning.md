At first glance, Q-Learning bears a great resemblance to [[SARSA]] as it also uses the idea of [[Policy Iteration]] with no known [[Markov Decision Process]]. The difference between the two lies in the fact that we do not bootstrap based on the action suggested by the policy $\pi$ but (with oracle intelligence) the optimal action among the feasible ones of the policy.

That means, Q-Learning iteratively runs two consecutive steps:

- Policy Evaluation:
	$$Q_\pi(S_t, A_t) \leftarrow Q_\pi(S_t, A_t) + \alpha(R_{t+1} + \gamma \max_{a \in \mathcal{A}} Q_\pi(S_{t+1}, a) - Q_\pi(S_t, A_t))$$
- Policy Improvement: use [[Epsilon-greedy Policy Improvement]] to greedily take actions among the greediest and exploratory ones.

Alternatively, we can see Q-learning as [[SARSA]]'s special case when $\pi$ is a greedy policy, i.e. $\pi(s) = \arg \max_{a \in \mathcal{A}} Q(s, a).$
	$$\begin{align}
	Q(S_{t+1}, A_{t+1}) &= Q(S_{t+1}, \pi(S_{t+1})) \\
	&= Q(S_{t+1}, \arg \max_{a \in \mathcal{A}} Q(S_{t+1}, a)) 
	= \max_{a \in \mathcal{A}} Q_\pi(S_{t+1}, a)
	\end{align}$$

***Pseudocode***:
![400](QLearning.png)

In fact, you can observe from the pseudocode that we have no specific next action update at the end of the inner loop compared to [[SARSA]]. Picking the optimal action means that it does not need to follow the current policy $\pi$ and the optimal action may not be followed in the next step.