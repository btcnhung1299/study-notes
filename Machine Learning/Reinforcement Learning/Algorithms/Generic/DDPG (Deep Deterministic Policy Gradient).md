DDPG [1] is a deep RL algorithm that acts on continous/stochastic policy.

### Components
DDPG employs [[Actor-Critic]] method with
- Actor network $\pi_\theta(s)$ and its target $\pi_{\theta^-}(s)$
- Critic network $Q_w(s,a)$ and its target $Q_{w^-}(s,a)$
- Experience replay buffer

### Flow
- Pool into a memory replay tuples of <state, action, reward> and randomly pick a batch of samples from this replay memory to compute loss and back-propagation. 

- Specially, two phases of optimization are carried out:
	1. Optimization of the critic $Q_w(s,a)$: use [[Gradient Descent]] to minimize the [[Mean Square Error (MSE)]] between the action values predicted by the target actor and our actor. As introduced, next action in the equation is predicted via the (target) critic.
	2. Optimization of the actor $\pi_\theta(s)$: basically [[Policy Gradient (Model-Free Policy-based RL)]] in which we try to maximize the total action values using gradient ascent.

- Periodically update the target actor and critic.

### Novelty

- To apply [[DQN (Deep Q-Network)]] for continuous action space, DDPG suggests actor network to predict next best actions instead of greedily searching $\max_{a \in \mathcal{A}} Q(s,a)$ which is infeasible.
- Inspired by [[DQN (Deep Q-Network)]], the authors use experience replay to break the correlations of consecutive samples.
- Inspired by [[DQN (Deep Q-Network)]], the authors use target networks to stablise the training.

***Pseudocode***:
![550](DDPG.PNG)

### Experimental settings


---
[1] [Continuous Control with Deep Reinforcement Learning](https://arxiv.org/abs/1509.02971)