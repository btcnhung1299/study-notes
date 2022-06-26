
# Abstract

QTRAN is a multi-agent reinforcement learning algorithm that employs centralised learning with decentralised execution. QTRAN improves [[QMIX (Q Mixing)]]/[[VDN (Value Decomposition Network)]] by allowing arbitrary factorisation instead of enforced with monotocity/additivity constraints.

# Description

### Components
1.  Local action-value network $Q_i(\tau_i, u_i)$ at each agent $i$
2. Joint action-value network $Q_{jt}(\boldsymbol{\tau}, \boldsymbol{u})$ (where $jt$ short for *joint*)
3. Transformed-joint action-value network $Q_{ji}^\prime(\boldsymbol{\tau}, \boldsymbol{u}) = \sum_i Q_i(\tau_i, u_i)$
4. Joint state-value network $V_{jt}(\boldsymbol{\tau})$ (inspired by [[Dueling Network]])

### Flow

![600](QTRAN.PNG)
1. Local network $Q_i$ computes action-values based on given local observations $\tau_i$. These action-values are used to decide next local action $u_i$.
2. Compute QTRAN's left-hand side equation $Q_{jt}^\prime(\boldsymbol{\tau}, \boldsymbol{u}) - Q_{jt}(\boldsymbol{\tau}, \mathbf{u}) + V_{jt}(\boldsymbol{\tau})$ by
	1. $Q^\prime_{jt}(\boldsymbol{\tau}, \boldsymbol{u}) = \sum_i Q_i(\tau_i, u_i)$
	2. Feed joint actions vector $\boldsymbol{\tau}$ as input to joint action-value network $Q_{jt}$ and joint state-value network $V_{jt}$ of choice
3. To allow abitrary representation, the network must satisfy
$$Q^\prime_{jt}(\boldsymbol{\tau}, \boldsymbol{u}) - Q_{jt}(\boldsymbol{\tau}, \boldsymbol{u}) + V_{jt}(\boldsymbol{\tau}) = 
\begin{cases}
0 & \mathbf{u} = \mathbf{\bar{u}} \\
\geq 0 & \mathbf{u} \ne \mathbf{\bar{u}} 
\end{cases} \tag{1}$$
	This condition is enforced in optimisation with three terms
$$L_{td} + \lambda_{opt} L_{opt} + \lambda_{nopt} L_{nopt}$$
	where
	- $L_{td} = \text{MSE}(Q_{jt}, y)$: optimise our approximation of joint action-value function with [[Mean Square Error (MSE)]]. See [[VDN (Value Decomposition Network)]] or [[QMIX (Q Mixing)]].
	- $L_{opt} = (Q_{jt}^\prime - Q_{jt} + V_{jt})^2$: optimise in case of optimal actions.
	- $L_{nopt} = [\min(Q^\prime_{jt} - Q_{jt} + V_{jt}, 0)]^2$: optimise in case of sub-optimal actions.

### Novelty

- Previous factorisation methods are limited in their representations due to restricted structural constraints (additivity in [[VDN (Value Decomposition Network)]], monotonicity in [[QMIX (Q Mixing)]]). The authors show that **we can arbitrarily represent any factorisable tasks as long as the constraints (1) are satisfied**.
- In the proposed conditions, the authors use joint state-values $V_{jt}$ to account for the discrepency between non-transformed $Q_{jt}$ and transformed $Q^\prime_{jt}$. On the other hand, $V_{jt}$ includes information of the global state that is unavailable in local observations.

### Experimental settings



“the joint action-value network shares the parameters  
at the lower layers of individual networks, where the joint  
action-value network combines hidden features with summa-  
tion Pi hQ,i(τi, ui) of hi(τi, ui) = [hQ,i(τi, ui), hV,i(τi)]  
from individual networks. This parameter sharing is used to  
enable scalable training with good sample efficiency at the  
expense of expressive power.” (Son et al., 2019, p. 4)

