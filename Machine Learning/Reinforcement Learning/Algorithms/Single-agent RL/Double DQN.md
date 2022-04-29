Double DQN [1] is an extension over [[DQN (Deep Q-Network)]], targets at deterministic policy.

### Components
All components in [[DQN (Deep Q-Network)]]:
- Action-value function approximation $Q_\theta(s,a)$ and its target network $Q_{\theta^-}(s,a)$
- Experience replay

### Flow
Mostly identical to the one in [[DQN (Deep Q-Network)]], except for the bootstrapping value:
- Pooling experience <state, action, reward, next state>
- Replay from memory a batch of experience and perform [[Mean Square Error (MSE)]] loss optimization that employs different network (particularly, target network) for evaluation
$$y = R_{t+1} + \gamma Q_\theta \left( S_{t+1}, \arg \max_{a \in \mathcal{A}} \underbrace{Q_{\theta^-}(S_{t+1}, a)}_{\text{instead of } Q_\theta(.) \text{ in standard DQN}} \right)$$
$$\mathcal{L}(\theta) = \mathbb{E} \left[ \left( y - Q_{\theta^-}(s,a) \right)^2 \right]$$

### Novelty

- The same networks are used for evaluation and action selection in [[DQN (Deep Q-Network)]]
	$$R_{t+1} + \gamma Q_\theta \left( S_{t+1}, \arg \max_{a \in \mathcal{A}} Q_\theta(S_{t+1}, a) \right)$$
	resulting in overestimation of action values, i.e. gives ridiculously high action values. The authors suggest decoupling into two different networks and use target network $Q_{\theta^-}$ for evaluation (supported by mathematical proof).
	$$R_{t+1} + \gamma Q_{\theta^-} \left( S_{t+1}, \arg \max_{a \in \mathcal{A}} Q_{\theta}(S_{t+1}, a) \right)$$

### Experimental settings

See [[DQN (Deep Q-Network)]]

---
[1] [Deep Reinforcement Learning with Double Q-learning](https://arxiv.org/abs/1509.06461)
