Markov Decision Process (MDP) mathematically describes agent decision making within an environment with ultimate goal is to minimise the expected sum of discounted reward.

A MDP can be described by a 5-element tuple
$$\langle \mathcal{S}, \mathcal{A}, R, P, \gamma \rangle$$
- $\mathcal{S}$ is the **state** space
- $\mathcal{A}$ is the **action** space
- $R: \mathcal{S} \times \mathcal{A} \rightarrow \mathbb{R}$ is the **reward** function that, together with [[discount factor]] $\gamma \in [0, 1)$, specifies [[return as cumulative onward reward]]
- $P$ is the so-called **transition probability** function  $p(s^\prime, r|s, a)= \Pr \{S_{t+1} = s^\prime, R_{t+1} = r | S_t = s, A_t =a\}$.
	<sub>This function has [[Markov property]], i.e. the next state $S_{t+1}$ (and its associated reward $R_{t+1}$) is fully determined by the action and the state in which that action is taken.</sub>

> **Observation**: A MDP assumes stationary environment. That is, $P$ is fixed and not a function of time. 

---

# FAQ

1. **Q**: How to refer a MDP with dynamic transition probability?
	**A**: When state transition is a function of time, it is called "non-stationary MDP".

2. **Q**: The connection among Markov process, Markov reward process, and Markov decision process?
	**A**: Start with description of the three
	- Markov process: $\langle \mathcal{S}, P \rangle$
	- Markov reward process $\langle \mathcal{S}, R, P, \gamma \rangle$
	- Markov decision process $\langle \mathcal{S}, \mathcal{A}, R, P, \gamma \rangle$
	
	It is easy to see that the Markov reward process is the Markov process with reward mechanism $R$ (and discount factor $\gamma$). In Markov decision process, we include agent decision state $\mathcal{A}$ to given Markov reward process.
	