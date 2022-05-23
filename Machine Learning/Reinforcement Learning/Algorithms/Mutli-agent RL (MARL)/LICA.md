LICA (**L**earning **I**mplicit **C**redit **A**ssignment) [1] is a multi-agent [[Actor-Critic]] algorithm that uses hypernetwork as an implicit representation which is informatic for credit assignment problem.

## Components

## Flow
1. Use behavioural cloning to extract policy $\pi^a$ from corresponding agent observation $z^a$ within a so-called **policy network (actor)**.
2. On the other hand, global state $s$ fed into different linear layers to create weights of the **mixing critic.** 
3. Then, the whole process uses [[Actor-Critic]] to optimise.

## Novelty
<sub>In [[MADDPG (Multi-agent DDPG)]], the critic $Q_\pi(s,a)$ associates state vector $s$ and action vector $a$ through ***addition***. Let's assume MLP as its structural architecture. Then, $q_i$ of sample $i$ is computed as: $q_i = \text{MLP}(\text{concat}(s_i, a_i)) = \text{MLP}(u_i) = \sum_{\theta_i} u_i$.</sub>
- In LICA, the authors suggest $Q_\pi(s,a)$ as a [[Hypernetwork]] in which the mixing of action vector and state vector (transformed) has multiplicative association.
- The author directly uses decentralised policies, i.e. policies of each agent, to optimise the joint action-value function.
- On the other hand, the authors propose **adaptive entropy regularisation** to improve the exploration of the algorithm, which is inherent policy-based approach.

## Experimental settings
![500](LICA.PNG)

---
[1] [Learning Implicit Credit Assignment for Cooperative Multi-Agent Reinforcement Learning](https://arxiv.org/abs/2007.02529)