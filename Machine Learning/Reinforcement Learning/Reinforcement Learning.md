**Ultimate goal**: In reinforcement learning problem, we want the agent to learn to act in order to maximise its goal. That is, for different type of RL, we want the following:
- Passive RL (fixed [[policy]] $\pi$): learn the [[state-value function (utility)]] $U$
- Active RL: learn the [[state-value function (utility)]] $U$ in association with the policy $\pi$ (that is balanced between exploitation and exploration)

**Reinforcement learning algorithms**:

*Q: Model-based RL vs. model-free RL?*
A: Model-based RL relies on model of the environment, i.e. the transition and reward function (e.g. [[Policy Evaluation]], [[Temporal-Difference (TD) Policy Evaluation]]), whereas it is not required or will be learned in model-free RL (e.g. [[Q-learning]]).

*Q: What does it mean to be a sample efficient RL?*
A: A sample efficient algorithm can make the most of all available samples. That is, it requires few samples, or demonstrations in RL, to reach a certain level of performance.

*Q: On-policy vs. off-policy algorithms?*
A: In off-policy algorithms, it can work with pre-collected data regardless of the policy used to obtain that data; whereas in on-policy algorithms, it must use the data collected with specific policy.

**Experiments**:
- Environments: https://gym.openai.com/envs/
- Results: plot charts of *return vs. timestep*

**Q-Learning**
Based on [[Bellman equation]] with $Q^\pi(s, a) = \mathbb{E}_{s'}[ r(s, a) + \mathbb{E}_{a' \sim \pi} Q^\pi(s', a')]$, adjust the parameter of Q-network as
$$\mathcal{L}(\theta) = \mathbb{E}_{s, a, r, s'}[(Q^\pi(s, a | \theta) - y)^2] \text{ where } y = r(s, a) + \gamma \max_{a'} \bar{Q}^\pi(s', a')$$
Q-Learning can be easily applied to problem with discrete action space because it concerns action-values function and thereby unsuitable for continuous problem.


**Policy Gradient**
Adjust the parameter of policy as by the direction that will give the most reward, i.e.
$$\mathcal{L}(\theta) = \mathbb{E}_{s \sim p^\pi, a \sim \pi_\theta}[R] = \mathbb{E}_{s \sim p^\pi, a \sim \pi_\theta}[\nabla_\theta \log \pi_{\theta} (a|s) Q^\pi(s, a)]$$

When we approximating $Q^\pi(s, a)$ (by Q-Learning), the method is called actor-critic.
Policy gradient, on the other hand, is natural for continuous problem because it concerns the policy itself (which is stochastic) while the action-value function can be approximated.