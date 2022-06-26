1. [[#Components|Components]]
1. [[#Flow|Flow]]
1. [[#Novelty|Novelty]]
1. [[#Experimental settings|Experimental settings]]


# Abstract
QMIX is a multi-agent reinforcement learning algorithm that employs centralised learning with decentralised execution paradigm. Extended from [[VDN (Value Decomposition Network)]], QMIX enforces monotonicity constraints between joint and local networks, and thereby increases representational capabilities compared to the previous additivity constraints in VDN.

# Description
## Components
QMIX contains two networks:
- Agent network $Q_i$ at each agent $i$
- Mixing network $Q_{tot}$ for centralised coordination. This network includes a hypernetwork to generate appropriate weights from additional state (which is not employed/available in local observations).

## Flow
![400](QMIX.PNG)

1. At timestep $t$, given local observation $o_t^i$ and previous action $u_{t-1}^i$, $Q_i(\tau^i, \cdot)$ computes action values, from which the locally optimal action $u_t^i$ is selected to be taken next (e.g. using [[Episilon-greedy]]).
2. $Q_{tot}(\tau, u)$ learns to combine agent action values $Q_i(\tau^i, u_t^i)$. Specifically, it first employs additional state $s_t$ to create network weights $w_{tot}$. This step is perfomed by the so-called **mixing network**. Subsequently, the model uses $w_{tot}$ to aggregate $Q_i(\tau^i, u_t^i)$. By optimisation, the model can be trained end-to-end by minimising [[Mean Square Error (MSE)]] as frequently employed, e.g. in [[DQN]].

## Novelty
- The algorithm relies on factorisation, which states that the local optimal actions selected from $Q_i(\tau_i, \cdot)$ are jointly optimal actions selected from $Q_{tot}(\tau, \cdot)$
$$\arg \max_u Q_{tot}(\tau, u) = 
\begin{pmatrix}
\arg \max_{u_1} Q_1(\tau_1, u_1) \\
\vdots \\ 
\arg \max_{u_n} Q_n(\tau_n, u_n) \\
\end{pmatrix}$$

- In previous work, i.e. [[VDN (Value Decomposition Network)]], the joint action values are guaranteed factorisable by enforcing additivity $Q_{tot} = \sum_{i} Q_i$. In QMIX, the authors **relax this constraint to motonocity** between joint and local action values, and thereby allow richer representation
	$$\frac{\delta Q_{tot}}{\delta Q_i} \geq 0, \forall i$$
	Intuitively, the constraint forces the optimisation direction to be the same for both local and joint action values. Practically, the authors demand for non-negative weights (described in [Flow](#flow), step 2) to comply with this constraint.
- Given that the weights must be non-negative and the mixing network must encode the additional state information, the authors employ [[Hypernetwork]] to embed state in network weights. The weights, outputed after an absolute operation, are used to combine $Q_i$.

## Experimental settings
The network is evaluated on SMAC challenges.
- The authors use [[DRQN (Deep Recurrent Q-Network)]] to create $Q_a(\tau_a, \cdot)$ from (local observation $o^a$, previous action $u_{t-1}^a$) at each agent $a$. The action values are used in [[Epsilon-greedy]] to select the next action $u_t^a$.
- The authors use [[FFN (Feed Forward Network)]] to create joint action values $Q_{tot}(\tau, u)$ from all local $Q_a(\tau_a, u_a)$.

