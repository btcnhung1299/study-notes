Bellman equation states that the [[value function]] of a state (and action) is the sum of its immediate reward and the upcoming rewards (either by expectation or optimal ones, which gives raise to Bellman Expectation and Bellman Optimality Equation).

> Application: Bellman equation can be used in prediction/planning (by using Bellman Expectation Equation to find the latent [[value function]]) and control (to find the optimal [[policy]] by using Bellman Optimality Equation)

## Bellman Expectation Equation

- From the definition of [[value function]]:
	$$\begin{align}
	Q(S_t = s, A_t = a)
	&= \mathbb{E} [G_t \mid S_t = s, A_t = a] \\
	&= \mathbb{E} [R_{t+1} + \gamma V(S_{t+1}) \mid S_t = s, A_t = a] \\
	&= \mathbb{E} \left\{ R_{t+1} + \gamma \mathbb{E}_{a^{\prime} \sim \pi} [Q(S_{t+1}, a^{\prime})] \mid S_t = s, A_t = a \right\}
	\end{align}$$
	or,
	$$Q(S_t, A_t) = R_{t+1}(S_t, A_t) + \gamma Q(S_{t+1}, A_{t+1})$$
	
	When we act accordingly to a specified [[policy]] $\pi$,
	$$
	\begin{align}
	Q_{\pi}(S_t = s, A_t = a)
	&= R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a  V_\pi(s^\prime) \\
	&= R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a \sum_{a^{\prime} \in \mathcal{A}} \pi(a^{\prime} \mid s^{\prime}) Q_{\pi}(s^{\prime}, a^{\prime})
	\end{align}
	$$
	where $P^a_{ss^{\prime}}$ refers to the [[transition probability]] from state $s$ to $s^{\prime}$ with action $a$.

- From the definition of [[state-value function (utility)]]:
	$$\begin{align}
	V(S_t = s) 
	&= \mathbb{E} [G_t \mid S_t =s] \\
	&= \mathbb{E} [R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots \mid S_t = s] \\
	&= \mathbb{E} [R_{t+1} + \gamma(R_{t+2} + \gamma R_{t+3} + \dots) \mid S_t = s] \\
	&= \mathbb{E} [R_{t+1} + \gamma V(S_{t+1}) \mid S_t = s]
	\end{align}$$
	or,
	$$V(S_t) = R_{t+1}(S_t, A_t) + \gamma V(S_{t+1})$$
	
	 When we act accordingly to a specified [[policy]] $\pi$,
	$$
	V_{\pi}(S_t = s)
	= \sum_{a \in \mathcal{A}} \pi(a \mid s) \left[ R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P^a_{ss^{\prime}} V_{\pi}(s^{\prime}) \right]
	$$
	where $P^a_{ss^{\prime}}$ refers to the [[transition probability]] from state $s$ to $s^{\prime}$ with action $a$.

	**Note**: Alternatively, we can derive above equation based on $V_\pi(s) = \sum_{a \in \mathcal{A}} \pi(a \mid s) Q_\pi(s,a)$.

> Observation: The [[value function]] of the current state (and action) is, in fact, dependent on the value of the next state.

## Bellman Optimality Equation

- In [[value function]]:
	$$\begin{align}
	Q_*(S_t = s, A_t = a) &= \max_{\pi} Q_\pi(s,a) \\
	&= R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a V_*(s^{\prime}) \\
	&= R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}}^a \max_{a^{\prime} \in \mathcal{A}} \left[ Q_*(s^{\prime}, a^{\prime}) \right]
	\end{align}
	$$

- In [[state-value function (utility)]]:
	$$\begin{align}
	V_{\pi^*}(S_t = s) &= \max_\pi V_\pi(s) \\
	&= \max_{a  \in \mathcal{A}} 
	\left[ R_{t+1}(s,a) + \gamma \sum_{s^{\prime} \in \mathcal{S}} P_{ss^{\prime}} V_*(s^{\prime}) \right]
	\end{align}
	$$
	
	Note: Alternatively, we can derive above equation based on $V_*(s) = \max_{a \in \mathcal{A}} Q_*(s,a)$

> Observation: The optimality equation involves non-linear operation (i.e. $\max$) and thus, there is no closed form solution. However, we can use iterative methods in [[Planning with given environment description using Dynamic Programming]] to find the optimal value function (and thus optimal policy) in a known [[Markov Decision Process (MDP)]].