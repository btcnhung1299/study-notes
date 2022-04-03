- Seek the explicit representation of reward function
Problems:
- Ambiguity: many policies are optimal with respect to the given value function and many value functions can explain the set of demonstrations.

Maximum entropy IRL: seek the value function with maximum entropy that matches the expected reward of the experts (aka. with the least commitment)
-> Problem: huge complexity because it requires integral over all trajectories
-> Adversial IRL can scale maximum entropy IRL: realise the sampling-based approximation in maximum entropy IRL by [[Generative Adversarial Network (GAM)]].