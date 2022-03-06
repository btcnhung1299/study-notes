
Intuition: The last direction is taken into account in the current update step.

Last direction: $v_{t-1}$

Update:
$$\theta = \theta - v_{t}$$
$$v_t = \gamma v_{t-1} + \eta \nabla_{\theta} J(\theta)$$

Usually $\gamma = 0.9$

*Note*:
- Parameters are updated as a whole, i.e., the same update for all parameters