Stabalised experience replay [1] modifies vanilla experience replay (in [[DQN]]) to account for the non-stationary transition dynamics in MARL. There are two solutions proposed: (1) to weight replays with [[Importance Sampling]] ratios, and (2) to condition agent policy on other agents' policies inferred from their behaviour (via their learnt parameters)

## Components

## Flow

## Novelty
<sub>In independent Q-learning (IQL), each agent learns an optimal policy based on [[value function]] conditioned on its own observations that satisfies the [[Bellman equation]]:
	$$Q^*(s, u_a | \pi_{-a}) = \sum_{\mathbf{u}_a} \pi_{-a}(-\mathbf{u}_a |s) \left[ r + \gamma \sum P(s^\prime | s, u_a, -\mathbf{u}_a) \max_{u^\prime_a} Q^*_a(s^\prime, u^\prime_a) \right]$$
	The term $\pi_{-a}(\mathbf{u}_{-a}|s)$ accounts for the non-stationary because it changes when the policies of other agents evolve over time.</sub>
	
Method 1:
- Learning in IQL is referred to as *off-environment* learning. The authors draw an analogy to *off-policy* and suggest using importance sampling to account of the changes in environment.
- Practically, each term in the loss function is weighted with important sampling ratio $\frac{\pi_{-a}^{t}(\mathbf{u}_{-a}|s)}{\pi_{-a}^{t_i}(\mathbf{u}_{-a}|s)}$ where $t$ is the the time of replay and $t_i$ is the time when $i$-th sample collected. As a result, obsolete replay decays over time.

Method 2:
- The individual Q-function can be made stationary by conditioned on other agents' policies. An naive approach would augment agent observation (input of Q-function) with weights of other agents' networks $O^\prime(s) = \{ O(s) ,\boldsymbol{\theta}_a \}$. This approach is infeasible in case of deep neural networks.
- ...

## Experimental settings
 Method 1: In replay buffer, we save tuples of $\langle s, u_a, r, s^\prime, \pi_{-a}(\mathbf{u}_{-a}|s) \rangle$.
 
 Method 2: Agent observation is augmented with the fingerprints derived from other agents' information. The fingerprint includes the training iteration number $e$ and exploratory rate $\epsilon$. In other words, we have augmented observation $O^\prime(s) = \{ O(s), e, \epsilon \}$.

# FAQ

---
[1] [Stabilising Experience Replay for Deep Multi-Agent Reinforcement Learning](https://arxiv.org/abs/1702.08887)