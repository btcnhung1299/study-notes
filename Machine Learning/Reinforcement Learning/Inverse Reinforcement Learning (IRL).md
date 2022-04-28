Explicit learn reward function, which potentially improves the performance and handle distributional mismatch between data applied learnt policy and expert policy.

Problems:
1. Ambiguity: many policies are optimal with respect to the given value function and many value functions can explain the set of demonstrations.

**Maximum entropy IRL**: seek the value function with maximum entropy that matches the expected reward of the experts (aka. with the least commitment)
-> Problem: huge complexity because it requires integral over all trajectories
-> Adversial IRL can scale maximum entropy IRL: realise the sampling-based approximation in maximum entropy IRL by [[Generative Adversarial Network (GAM)]].