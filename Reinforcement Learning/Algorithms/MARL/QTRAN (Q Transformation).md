
QTRAN [1] is a multi-agent reinforcement learning algorithm that allows centralised learning with decentralised execution. QTRAN is improved over [[QMIX (Q Mixing)]]/[[Value Decomposition Network (VDN)]] as it allows arbitrary factorisation.

### Components
1. Joint action-value network $Q_{jt}$
2. Local action-value network $Q_i$
3. State-value network (similar to [[Dueling Network]])
4. The summation network $Q_{ji}^\prime = \sum Q_i$

### Flow
1. Each local network $Q_i$ outputs a selected local action $u_i$ based on their action values.
2. On one hand, the values $Q_i$ are summed to create $Q_{ji}^\prime$. On the other hand, joint actions $\mathbf{u}$ are inputs to compute joint action values $Q_{jt}$.
3. The network is optimise to satisfy
$$\sum_i Q_i(\tau_i, u_i) - Q_{jt}(\tau, \mathbf{u}) + V_{jt}(\tau) = 
\begin{cases}
0 & \mathbf{u} = \mathbf{\bar{u}} \\
\geq 0 & \mathbf{u} \ne \mathbf{\bar{u}}
\end{cases}$$
via the combined losses
$$L_{td} + \alpha L_{opt} + \beta L_{noopt}$$
where
- $L_{td} = \text{MSE}(Q_{jt}, y)$
- $L_{opt} = (1)^2$
- $L_{noopt} = (min((1), 0)^2)$

### Novelty

### Overall architecture

### Experimental settings


---

[1] [QTRAN: Learning to Factorize with Transformation for Cooperative Multi-Agent Reinforcement Learning](https://arxiv.org/abs/1905.05408)