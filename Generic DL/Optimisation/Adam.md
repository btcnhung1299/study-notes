**Ada**ptive **M**oment Estimation

- Subject: stochastic (or "noisy") objective function
	<details>Stochasticity might come from data subsampling (minibatches of data samples), dropout regularisation, etc.</details>

**Procedure**:
Let gradient at the timestep $t$ is $g_t$, or $g_t \leftarrow \nabla_{\theta}J(\theta_{t-1})$
1. Inspired by [[AdaGrad]], the update step utilises both the gradient $g_t$ and the squared gradient $g_t^2$.
	What's more, it takes their moment estimate, namely $m_t$ (momemt estimate of the gradient) and $v_t$ (moment estimate of the squared gradient), controlled by the decay rates $\beta_1$ and $\beta_2$ (see [[Momentum]]).
	$$m_t \leftarrow \beta_1 m_{t-1} + (1-\beta_1) g_t$$
	$$v_t \leftarrow \beta_2 v_{t-1} + (1-\beta_2) g_t^2$$
2. These estimates are biased (towards 0 due to the initialisation). Therefore, we divide them with appropriate term to correct biases:
	$$\widehat{m}_t \leftarrow \frac{m_t}{1-\beta_1^t}$$
	$$\widehat{v}_t \leftarrow \frac{v_t}{1-\beta_2^t}$$
3. Finally, we take the similar update to [[AdaGrad]]:
	$$\theta_t \leftarrow \theta_{t-1} - \eta \frac{\widehat{m}_t}{\sqrt{\widehat{v}_t  + \epsilon}}$$
	where $\epsilon$ is the smoothing term to avoid division by 0.

---
*Q: Why the second decay rate $\beta_2$ is often chosen to be larger than $\beta_1$* (best practice suggests $\beta_1=0.9, \beta_2=0.999$)

[1] Adam: A Method for Stochastic Optimization