BCQ [1], or **B**atch-**C**onstrained **Q**-learning, is an offline reinforcement learning algorithm. BCQ explicitly minimises the mismatch in value estimation induced in learnt policy and behaviour policy to address extrapolation error.

## Novelty
<sub>Previous works resort to experience replay in batch (e.g. [[DQN (Deep Q-Network)]]). However, this method only works when there is correlation between the batch distribution and distribution under the current policy. The constraint is not guaranteed because of extrapolation error. As a result, exploratory actions in near-on-policies such as $\epsilon$-greedy suffer from poor value estimation caused by extrapolation error.</sub>

- The authors prove that the (tabular) extrapolation error is discarded (i.e. $\epsilon_{MDP}^\pi = 0$) as long as the overall [[Markov Decision Process]] and batch-specific one demonstrates the same transition probabilities in regions of relevence. As a result, the authors define batch-constrained policy ... Practically, the authors use conditional [[Variational Autoencoder (VAE)]] to generate batch-constrained policy and perturbation network to increase diversity.
	$$\begin{gather*}
	a_i^\prime = a_i + \underbrace{\xi(s, a_i, \Phi)}_{\text{perturbation network}}, a_i \sim G_\omega(s) \\
	\pi(s) = \arg \max_{a_i^\prime} Q(s, a_i^\prime)
	\end{gather*}$$

## Experimental settings
BCQ is evaluated on MuJoCo.

---

[1] [Off-Policy Deep Reinforcement Learning without Exploration](https://arxiv.org/abs/1812.02900)