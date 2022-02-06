**Original paper**: [Continuous Control with Deep Reinforcement Learning](https://arxiv.org/abs/1509.02971)

Naturally, one might want to extend [[DQN (Deep Q-Network)]] in continuous action space. However, it is practically infeasible as DQN requires significant resources to find greedy action in $\max_{a \in \mathcal{A}} Q(s,a)$ given continous action space. Hence, based on [[Actor-Critic]] method, DDPG **employs an actor that would learn to suggest the best action**. DDPG employs experience replay and target network to make the training more stable, as successfully proven in DQN.

- Let our critic $Q_w(s,a)$ and our actor $\pi_\theta(s)$

- Pool into a memory replay tuples of <state, action, reward> and randomly pick a batch of samples from this replay memory to compute loss and back-propagation. This experience replay is claimed to break the correlations of consecutive samples.

- Two phases of optimization are carried out:
	1. Optimization of the critic $Q_w(s,a)$: use [[Gradient Descent]] to minimize the [[Mean Square Error (MSE)]] between the action values predicted by the target actor and our actor. As introduced, next action in the equation is predicted via the (target) critic.
	2. Optimization of the actor $\pi_\theta(s)$: basically [[Policy Gradient (Model-Free Policy-based RL)]] in which we try to maximize the total action values using gradient ascent.


***Pseudocode***:
![550](../resources/DDPG.png)