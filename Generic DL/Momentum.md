Last direction: $v_{t-1}$

Update:
$$\theta = \theta - v_{t}$$
$$v_t = \gamma v_{t-1} + \eta \nabla_{\theta} J(\theta)$$

Usually $\gamma = 0.9$