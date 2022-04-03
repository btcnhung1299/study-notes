Markov Game (MG), or stochastic game, "extends game theory to [[Markov Decision Process (MDP)]]-like environments".
> **Application**: MG is frequently used to mathematically describe the environment settings for [[Multi-agent Reinforcement Learning (MARL)]].

A MG can be described by a tuple
$$\langle \mathcal{I}, \mathcal{S}, \{\mathcal{A}_i\}_{i=1}^k, \{R_i\}_{i=1}^k, \mathcal{T}, \gamma \rangle$$

- $\mathcal{I} = \{ 1, ..., k \}$ is a finite set of players/agents
- $\mathcal{S}$ is the state space
- $\mathcal{A}_i$ is the action space of agent $i$
- $R_i: \mathcal{S} \times \mathcal{A}_1 \times ... \times \mathcal{A}_k \rightarrow \mathbb{R}$ is reward function of agent $i$
- $T: \mathcal{S} \times \mathcal{A}_1 \times ... \times \mathcal{A}_k \rightarrow (0,1)$ is the state **transition dynamics**
- $\gamma$ is [[discount factor]] ($0 \leq \gamma \lt 1$)

# FAQ
1. **Q**: Why it is called "stochastic game"?
	**A**: Because the optimal policy in MG can be stochastic (?)