**Original paper**: [Deep Recurrent Q-Learning for Partially Observable MDPs](https://arxiv.org/abs/1507.06527)

Observed that [[DQN]] only makes use of the current state while in fact, the state are dependent on the previous states, the authors suggest replace the final [[FFN (Feed Forward Network)]] layer before output by the [[Recurrent Neural Network (RNN)]] to enhance the sequential information.

*Note:* Despite the straightforward idea, the experimental section is rather weak.