# Abstract
MADDPG (Multi-agent DDPG) [1] is a multi-agent reinforcement learning algorithm that extends [[DDPG (Deep Deterministic Policy Gradient)]] for multi-agent scenarios. It employs actor-critic approach where each agent has its corresponding centralised critic.

# Description
## Components

## Flow

## Novelty
- The authors suggest that the environment will become stationary once we know all the actions taken by other agents, regardless of the policy evolvement. Hence, the idea is to have local Q-function conditions on all actions, i.e. $Q_i(\mathbf{x}, a_{1:n})$


## Experimental settings