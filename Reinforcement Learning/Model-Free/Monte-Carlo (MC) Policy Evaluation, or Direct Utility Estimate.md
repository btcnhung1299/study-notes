#### Description
Given a policy, we want to find [[value function]] while having no information about the [[Markov Decision Process]] behind the environment.

#### Algorithm
**A. Description**
- Directly keep a running average of total [[value function]] at each state in different trials or [[episode, or trajectory]].  By the law of large number, the more observations we get for this value at state $s$, the closer it gets to the true expectation of the target value function at that state.

**Note 1**: For each state, we can either consider its first appearance (result in *First-visit MC policy evaluation*) or its every appearance (result in *Every-visit MC policy evaluation*) in tracking.

**Note 2**: Mean tracking can be done online with incremental method, see below.

> Observation: We need to see **complete episodes** in order to get the return at each state, which is infeasible with infinite process or offline learning (mostly).

**B. Pseudocode**
![500](../resources/MCPrediction.png)

**C. Online version**

We can derive the online MC policy evaluation by updating average incrementally.
$$
\begin{align}
\mu_k = \frac{1}{k} \sum_{i=1}^k x_i 
&= \frac{1}{k} \left( x_k + \sum_{i=1}^{k-1} x_i \right) \\
&= \frac{1}{k} x_k + \frac{1}{k} (k-1) \mu_{k-1} \\
&= \mu_{k-1} + \frac{1}{k} (x_k - \mu_{k-1})
\end{align}$$



**Disadvantage**:
- Violate the nature of states, or [[Bellman equation]]: states are not independent from each other -> slow converge