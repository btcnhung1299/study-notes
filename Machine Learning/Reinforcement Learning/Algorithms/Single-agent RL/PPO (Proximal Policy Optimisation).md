# Abstract
Proximal Policy Approximation (PPO) is a data-efficient algorithm that relies on policy gradient. Particularly, it uses trust region policy optimisation (TRPO) to enable policy updates using minibatches. The algorithm proposes objective function with clipped probability ratios that forms the lower bound on policy performance.

# Description
## Components
The same as [[Policy Gradient (Model-Free Policy-based RL)]]

## Flow
The same as [[Policy Gradient (Model-Free Policy-based RL)]] but with novel objective function.

## Novelty
- Empirically, it is a bad idea to naively perform minibatch updates on [[Policy Gradient (Model-Free Policy-based RL)]] objective because the updates can be destructively large. On the other hand, TRPO is an objective function that proposes constraint on the size of the policy update
  $$\begin{align}
  \max_{\theta} \hat{\mathbb{E}}_t \left[\frac{\pi_\theta(a_t|s_t)}{\pi_{\theta_{old}}(a_t|s_t)} \hat{A}_t \right] \\
  \text{subject to } \hat{\mathbb{E}}_t \left\{ \text{KL}[\pi_{\theta_{old}}(\cdot, s_t), \theta(\cdot, s_t)] \right\} \leq \delta
  \end{align}$$
  or equivalently,
  $$\max_{\theta} \hat{\mathbb{E}}_t \left\{ \frac{\pi_\theta(a_t|s_t)}{\pi_{\theta_{old}}(a_t|s_t)}\hat{A}_t  - \beta \text{KL}[\pi_{\theta_{old}}(\cdot, s_t), \theta(\cdot, s_t)] \right\} \tag{1}$$
  Naturally, the authors want to employ TRPO to limit the policy update size.
  - The authors suggest 2 different ways to improve the original TRPO:
	  1. Penalise the current objective function when the update is large. Particularly, the authors suggest **clipped surrogate objective** that removes the incentive for moving the probability ratio $r_t(\theta) = \frac{\pi_\theta(a_t|s_t)}{\pi_{\theta_{old}}}$ outside $[1-\epsilon, 1 + \epsilon]$ and taking the min as lower bound on the unclipped objective
	     $$\max_{\theta}\hat{\mathbb{E}}_t \left\{ \min \left[ r_t(\theta) \hat{A}_t, \text{clip}(r_t(\theta), 1 - \epsilon, 1 + \epsilon) \hat{A}_t \right] \right\}$$
	     ![800](PPO_obj.PNG)
	  2. In practice, it is hard to choose a fixed penalty coefficient $\beta$ for different problems or even in a single problem with constant changing characteristics over the course of learning. Therefore, the authors suggest **adaptive KL penalty coefficient** that will change $\beta$ according to current KL terms $d = \hat{\mathbb{E}}_t \left\{ \text{KL}[\pi_{\theta_{old}}(\cdot, s_t), \theta(\cdot, s_t)] \right\}$:
	    - $d < d_{targ} \div 1.5, \beta \leftarrow \beta \div / 2$
	    - $d > d_{targ} \times 1.5, \beta \leftarrow \beta \times 2$ 
	      *This improvement can be used as alternative or addition* method to the clipped surrogate objective.

## Experimental settings
The algorithm is evaluated on simulated robotic locomotion and Atari game playing.
