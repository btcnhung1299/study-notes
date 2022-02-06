**Original paper**: [QMIX: Monotonic Value Function Factorisation for Deep Multi-Agent Reinforcement Learning](https://arxiv.org/abs/1803.11485)

QMIX is a RL algorithm that aims to solve multi-agent scenario, in which we centrally train the algorithms as simuteneously train decentralized agents on their local data. Given $n$ agents, we will have $n$ local models to predict $Q_a$ and a global model $Q_{tot}$ to predict on the joint observation (of the ally) enhanced with other state information. These information is later fused to suggest decentralized action at each client.

To make the training effectively, we need to ensure the $\arg \max$ in of the global $Q_{tot}$ is the same as the $\arg \max$ in each of the agent $Q_a$ by enforce motonocity $\frac{\delta Q_{tot}}{\delta Q_a} \geq 0, \forall a$, which allows larger and richer representation.

QMIX uses two kind of networks:
- Agent network: uses [[DRQN (Deep Recurrent Q-Network)]] $Q_i(\tau^a, u^a)$
- Mixing network: [[FFN (Feed Forward Network)]] (inputs are $Q_i$)