 LOLA (**L**earning with **O**pponent-**L**earning **A**wareness) [1] is a [[Multi-agent Reinforcement Learning (MARL)]] algorithm. It suggests a novel term that accounts for changes in other agents' policy in optimisation of the current agent's policy.

## Components
In the standpoint of agent $i$:
- Agent policy network with parameters $\theta_i$
- Opponents (i.e. other agents) behavioural cloning network $\hat{\theta}_j$ where $j \neq i$

## Flow

## Novelty
<sub>In naive learner, agent $i$ takes a step of update towards
$$\Delta \theta_i = \nabla_{\theta_i} V_i(\theta_1, \ldots, \theta_k) \cdot \delta$$
where $k$ is number of agents and $\delta$ is step size for the update.</sub>

- The authors claim that naive learner might fail to find global/cooporative optimal strategy because it ignores the impact of other agents' policies when updating current agent's policy. They then suggest optimisation with respect to policies after update, $\theta_j + \Delta_{\theta_j}$ where $j \neq i$.
	
	For example, update rule for agent 1 in a game with $k=2$ is
	$$\Delta^\prime \theta_1 = \nabla_{\theta_1} V_1(\theta_1, \theta_2 + \Delta \theta_2) \tag{1}$$
	where $\Delta \theta_2 = \nabla_{\theta_2} V_2(\theta_1, \theta_2)$ is the update obtained by following naive learner. This update can be approximated by first-order [[Taylor series]]
	$$V_1(\theta_1, \theta_2 + \Delta \theta_2) \approx V_1(\theta_1, \theta_2) + (\Delta \theta_2)^\intercal \nabla_{\theta_2} V_1(\theta_1, \theta_2) \tag{2}$$
	
	Substitute (2) to (1), we arrive at the **LOLA update rule**
	$$\Delta^\prime \theta_1 = 
	\Delta \theta_1 + 
	\underbrace{(\nabla_{\theta_2} V_1)^\intercal}_{\text{part 1}} \
	\underbrace{\nabla_{\theta_1} \nabla_{\theta_2} V_2 \cdot \eta}_{\text{part 2}} \tag{3}$$
	where $\eta$ is step size. Note that $\nabla_{\theta_1}$ is intentionally removed from part 1 because the authors want to shape other agents' learning direction but not the other way around.
	
	Intuitively, part 1 in equation (3) describes how changes in agent 2 can affect agent 1's value whereas part 2 describes learning direction of agent 2. As the whole, the equation measures how agent 1 can change agent 2's learning step to increase agent 1's reward [2].
	
- [[Policy Gradient (Model-Free Policy-based RL)]] is suggested to approximate exact gradient and Hessian matrix in (3).
	
- Opponents' parameters are inferred from their trajectories with [[Behavioural Cloning (BC)]], complying to adversarial settings.

## Experimental settings
Evaluated on iterated [[Prisoner's Dilemma]].

# FAQ

---
[1] [Learning with Opponent-Learning Awareness](https://arxiv.org/abs/1709.04326)
[2] [OpenAI Blog - Learning to Model Other Minds](https://openai.com/blog/learning-to-model-other-minds/)