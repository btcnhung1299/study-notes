Markov Decision Process describes the environment (via states, rewards, transitions) and our decision process (via actions).

$$\langle \mathcal{S}, \mathcal{A}, R, P, \gamma \rangle$$
- $\mathcal{S}$ is state space
- $\mathcal{A}$ is action space
- $R$ is [[Return as cumulative onward reward]]
- $P$ is transition probability function with [[Markov property]], i.e. the next state is fully determined by the current state $P(S_{t+1} \mid S_t) = P(S_{t+1} \mid S_1, \dots, S_t)$
- $\gamma$ is [[Discount factor]], $0 \leq \gamma \leq 1$

---

# FAQ

1. Q: How to describe a decision process in which the transition probability is not fixed?
	A: It is described as a "non-stationary Markov decision process"

2. Q: What is the relation between Markov process, Markov reward process, and Markov decision process?
	A: Let's consider the formulation of the three:
	- Markov process: $\langle \mathcal{S}, P \rangle$
	- Markov reward process $\langle \mathcal{S}, R, P, \gamma \rangle$
	- Markov decision process $\langle \mathcal{S}, \mathcal{A}, R, P, \gamma \rangle$
	
	It is easy to see that the Markov reward process is the Markov process with reward mechanism via reward function $R$ and discount factor $\gamma$. In Markov decision process, we integrate our own decisions of actions $\mathcal{A}$.