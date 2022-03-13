**Original paper**: [Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602)

Basically, DQN (Deep Q-Network) is [[Q-learning]] with [[Value Function Approximation]] applied to [[Action-value Function, or Q-function]]. DQN is enhanced with **experience replay** and **target network** to make the training with deep neural networks more stable.

- In experience replay, all samples (i.e. a tuple of non-terminal <state, action, reward>) are pooled to a replay memory. A minibatch of samples are randomly chosen for optimization to break correlation among consecutive samples.

- Target network is used to compute optimal next action, which is periodically updated after a specific number of iterations.

- Optimization is done via [[Gradient Descent]] with the objective to minimize the [[Mean Square Error (MSE)]] between the action values predicted by the target network and our network.

***Pseudocode***:
![500](DQN.PNG)
