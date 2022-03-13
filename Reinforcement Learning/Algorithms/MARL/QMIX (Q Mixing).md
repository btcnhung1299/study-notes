QMIX [1] is a multi-agent reinforcement learning algorithm that employs centralised learning with decentralised execution. Extended from [[Value Decomposition Network (VDN)]], QMIX enforces monotonicity constraints between joint and local networks, and thereby increases representational capabilities compared with previous additivity constraints.

## Components
QMIX contains two networks:
- Agent network $Q_i$ at each agent $i$
- Mixing network $Q_{tot}$ for centralised coordination. This network includes a hypernetwork to generate appropriate weights from additional state (not available in local observations).

## Flow
![400](QMIX.PNG)

1. Given local observation $o_t^i$ and previous action $u_{t-1}^i$, $Q_i(\tau_i, \cdot)$ computes action values, from which the locally optimal action $u_t^i$ is selected.
2. Given additional state $s_t$, the hypernetwork computes weights $w_{tot}$ that embeds this information. The mixing network $Q_{tot}(\tau, u)$ then uses $w_{tot}$ to linearly combine all $Q_i$, intuitively generates action value conditioned on joint trajectory $\tau$ and actions $u$. We train $Q_{tot}$ in an end-to-end manner by minimising [[Mean Square Error (MSE)]] with respect to the observed action values.

## Novelty
<sub>The algorithm relies on factorisation, which states that the local optimal actions selected from $Q_i(\tau_i, \cdot)$ are jointly optimal actions selected from $Q_{tot}(\tau, \cdot)$, or
$$\arg \max_u Q_{tot}(\tau, u) = 
\begin{pmatrix}
\arg \max_{u_1} Q_1(\tau_1, u_1) \\
\vdots \\ 
\arg \max_{u_n} Q_n(\tau_n, u_n) \\
\end{pmatrix}$$
</sub>

- In previous work, i.e. [[Value Decomposition Network (VDN)]], the joint action values are guaranteed factorisation by overly enforcing additivity $Q_{tot} = \sum_{i} Q_i$. In QMIX, the authors relax this constraint to motonocity between joint and local action values, and thereby allow richer representation
	$$\frac{\delta Q_{tot}}{\delta Q_i} \geq 0, \forall i$$
	Intuitively, it ensures we follow the same optimisation direction for both local and joint action values. Practically, the authors demand for non-negative weights (described in [Flow](#flow), step 2) to comply with this constraint.
- Given that the weights must be non-negative and the mixing network must encode the additional state information, the authors suggest hypernetwork to embed state in network weights. The weights, outputted after an absolute operation, are used to combine $Q_i$.

## Experimental settings
The network is evaluated on SMAC challenges.
- Locally at each agent, we use [[DRQN (Deep Recurrent Q-Network)]] to create $Q_a(\tau_a, \cdot)$ from (local observation $o^a$, previous action $u_{t-1}^a$). The action values are used in [[Epsilon-greedy Policy Improvement]] to select the next action $u_t^a$.
- We use [[FFN (Feed Forward Network)]] to create joint action values $Q_{tot}(\tau, u)$ from all local $Q_a(\tau_a, u_a)$.


---

[1] [QMIX: Monotonic Value Function Factorisation for Deep Multi-Agent Reinforcement Learning](https://arxiv.org/abs/1803.11485)