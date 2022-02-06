**Purpose**:
- Define generative behavioral cloning, particularly for multi-agent enviroment
- Propose a hierarchical policy class

**1. Generative behavioral cloning in multi-agent scenario**
- Objective: mimic the expert all-agent actions $\mathbf{a}_t$ by finding the appropriate stochastic policy  $\pi_{\theta}$ that ouputs an action with respect to current all-agent state $\mathbf{x}_t$ and previous [[Episode, or Trajectory]] $\tau_t$
	$$\theta^{*} = \arg \min_{\theta} \sum_{t=1}^{T} \mathcal{l}\left[ \mathbf{a}_t, \pi_{\theta}(\mathbf{x}_t, \tau_{t-1}) \right]$$
	where $T$ is time horizon.

	**Problem-specific assumption**: For basketball game, transition is deterministic $\mathbf{x}_{t+1} = \mathbf{x}_t + \mathbf{a}_t$. Hence, the objective becomes
	$$\theta^{*} = \arg \min_{\theta} \sum_{t=1}^{T} \mathcal{l}\left[ \mathbf{x}_t, \pi_{\theta}(\tau_{t-1}) \right]$$
- We can use [[Maximum Likelihood Estimate (MLE)]] to solve above equation, i.e.
	$$\theta^{*} = \arg \min_{\theta} \sum_{t=1}^{T} p_{\theta}(\mathbf{x}_t \mid \tau_{t-1}) \tag{1}$$
	Intuitively, we want our target state $\mathbf{x}_t$ appears as with the highest probability given the history $\tau_{t-1}$

