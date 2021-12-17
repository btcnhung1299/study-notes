**Policy**: a function mapping [[state]] (or more accurately, observation) to action, or decide the next action based on the current state.
*Note*: In Deep RL, we typically model the policy by a neural network with parameters $\theta$ whose input has *the dimension of observation* and *output has the dimension of action*.

**Policy representation**:
*Best practice*: Policy representation, parameterised by $\theta$, shouldn't discontinuous function (recommended to be continuous) because it will exist $\theta$ that causes the policy switch from one action to another [0]

For example, a discontinuous policy given by
$$\pi(s) = \max_{a} \hat{Q}_{\theta}(s,a)$$
is typically replaced by **stochastic policy representation**, e.g. applying softmax function: 
$$\pi_{\theta}(s) = \text{softmax}\left[ \hat{Q}_{\theta}(s,a) \right]$$

**Optimal policy**:
The optimal policy is the policy that gives maximum [[Utility]] *starting from the initial state*. That is, given a state $s$, it picks the best action $a$ such that the expected utility:
$$\begin{align}
\pi^{*}(s) &= \arg \max_{\pi} U^{\pi} \\
&= \arg \max_{a} \sum_{s^{\prime}} P(s^{\prime} \mid s, a) U(s^{\prime})
\end{align}
$$


---
*References*:
[0] Artificial Intelligence: A Modern Approach