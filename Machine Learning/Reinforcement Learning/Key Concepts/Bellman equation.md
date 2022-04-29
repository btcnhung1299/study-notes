Bellman equation states that the [[value function]] is summation of immediate reward and the upcoming [[return (cumulative reward)]]. The Bellman equation shows the relation between two adjacency timesteps, which is particularly useful for dynamic programming approach.

There are two types of Bellman equation: (1) the Bellman Expectation Equation concerns all possible actions defined by [[policy]] when computing value function; and (2) Bellman Optimality Equation defines when optimal policy is followed.

## 1. Bellman Expectation Equation
We can obtain Bellman Expectation Equation

- From the definition of action-[[value function]]:
	$$\begin{align}
	Q(S_t = s, A_t = a)
	&= \mathbb{E} [G_t \mid S_t = s, A_t = a] \\
	&= \mathbb{E} [R_{t+1} + \gamma V(S_{t+1}) \mid S_t = s, A_t = a] \\
	&= \mathbb{E} \left\{ R_{t+1} + \gamma \mathbb{E}_{a'} [Q(S_{t+1}, a')] \mid S_t = s, A_t = a \right\}
	\end{align}$$
	or,
	$$\boxed{Q(S_t, A_t) = R_{t+1}(S_t, A_t) + \gamma Q(S_{t+1}, A_{t+1})}$$
	
	When we act accordingly to [[policy]] $\pi$,
	$$
	\begin{align}
	Q_{\pi}(S_t = s, A_t = a)
	&= \mathbb{E}_\pi \{ R_{t+1} + \gamma \mathbb{E}_{a' \sim \pi}[Q(S_{t+1}, a')] \}
	\\
	&= R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a \sum_{a^{\prime} \in \mathcal{A}} \pi(a^{\prime} \mid s^{\prime}) Q_{\pi}(s^{\prime}, a^{\prime})
	\end{align}
	$$
	where $P^a_{ss^{\prime}}$ refers to the [[transition probability]] from state $s$ to $s^{\prime}$ by taking action $a$.

- From the definition of state-[[value function]]:
	$$\begin{align}
	V(S_t = s) 
	&= \mathbb{E} [G_t \mid S_t =s] \\
	&= \mathbb{E} [R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots \mid S_t = s] \\
	&= \mathbb{E} [R_{t+1} + \gamma V(S_{t+1}) \mid S_t = s]
	\end{align}$$
	or,
	$$\boxed{V(S_t) = R_{t+1}(S_t, A_t) + \gamma V(S_{t+1})}$$
	
	 When we act accordingly to [[policy]] $\pi$,
	$$V_{\pi}(S_t = s)
	= \sum_{a \in \mathcal{A}} \pi(a \mid s) Q_\pi(s,a) =\sum_{a \in \mathcal{A}} \pi(a \mid s) \left[ R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P^a_{ss^{\prime}} V_{\pi}(s^{\prime}) \right]
	$$

**Application**: The dependency shown in Bellman Expectation Equation can be exploited for prediction/planning, i.e. to find the latent value function by dynamic programming.

## 2. Bellman Optimality Equation

- In terms of action-[[value function]]:
	$$Q_*(S_t = s, A_t = a) = \max_{\pi} Q_\pi(s,a) = R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a \max_{a^{\prime} \in \mathcal{A}} \left[ Q_*(s^{\prime}, a^{\prime}) \right]
	$$

- In terms of state-[[value function]]:
	$$V_{\pi^*}(S_t = s) = \max_\pi V_\pi(s) \\
	= \max_{a  \in \mathcal{A}} 
	\left[ R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}} V_*(s^{\prime}) \right]$$
	
> Observation: The Bellman Optimality Equation involves non-linear operation (i.e. $\max$) and thereby there is no closed form solution. However, we can use iterative methods in [[Planning with given environment description using Dynamic Programming]] to find the optimal value function (and thus optimal policy) in a known [[Markov Decision Process (MDP)]].