Motivation: Learn the policy based on feedbacks of implicit reward function from expert demonstration.

Settings: [[Markov Decision Process (MDP)]] where reward function $R$ is discarded but implicitly included by a collection of expert demonstrations where a demonstration is $\xi = \{ (s_0, a_0), (s_1, a_1), \ldots \}$

Goal: Learn a [[policy]] $\pi$ that imitates the expert policy $\pi^*$ implicitly inferred in expert demonstrations $\Xi = \{ \xi_1, \ldots, \xi_D \}$ where $D$ is number of demonstrations.

Approaches:
1. [[Behavioural Cloning (BC)]]: directly imitate expert's policy by seeking a function that maps states to actions
2. [[Inverse Reinforcement Learning (IRL)]]: indirectly imitate via modelling expert's reward function, which is used to infer expert's policy.

Observations: BC doesn't provide reasons (e.g. reward function) for its policy.