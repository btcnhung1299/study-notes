COMA (Counterfactual Multi-agent) [1] is an [[Actor-Critic]] algorithm that uses the so-called counterfactual baseline...

## Components

## Flow
<sub>In [[Independent Q-learning (IQL)]] (or particularly indepdent actor-critic), the critic optimises [[Temporal-Difference (TD) Policy Iteration]] with regard to the global reward. This approach fails to capture credit assignment of each agent.</sub>

- In COMA, critic optimisation uses so-called **counterfactual baseline** where the difference reward of an agent $a$ is given by $D^a = r(s, \mathbf{u}) = r(s, (\mathbf{u}^{-a}, c^a))$, denoting the reward with compared to when the default action $c^a$ taken. Since hard-coding default actions are time-consuming, the authors of COMA suggest the use of advantage function $A$ that can be directly learnt from experiences
	$$A^a(s,\mathbf{u}) = Q(s, \mathbf{u}) - \sum_{u'^a} \pi^a(u'^a | \tau^a) Q(s, \mathbf{u}^{-a}, u'^a)$$
## Novelty

---
[1] [Counterfactual Multi-Agent Policy Gradients](https://arxiv.org/abs/1705.08926)