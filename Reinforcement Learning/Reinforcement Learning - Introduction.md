**Ultimate goal**: In reinforcement learning problem, we want the agent to learn to act in order to maximise its goal. That is, for different type of RL, we want the following:
- Passive RL (fixed [[policy]] $\pi$): learn the [[state-value function, or utility]] $U$
- Active RL: learn the [[state-value function, or utility]] $U$ in association with the policy $\pi$ (that is balanced between exploitation and exploration)

**Reinforcement learning algorithms**:

*Q: Model-based RL vs. model-free RL?*
A: Model-based RL relies on model of the environment, i.e. the transition and reward function (e.g. [[Policy Evaluation]], [[Temporal-Difference (TD)]]), whereas it is not required or will be learned in model-free RL (e.g. [[Q-Learning]]).

*Q: What does it mean to be a sample efficient RL?*
A: A sample efficient algorithm can make the most of all available samples. That is, it requires few samples, or demonstrations in RL, to reach a certain level of performance.

*Q: On-policy vs. off-policy algorithms?*
A: In off-policy algorithms, it can work with pre-collected data regardless of the policy used to obtain that data; whereas in on-policy algorithms, it must use the data collected with specific policy.

**Experiments**:
- Environments: https://gym.openai.com/envs/
- Results: plot charts of *return vs. timestep*