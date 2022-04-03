#### Description
Given a policy, we want to **predict** [[value function]] while having no information about the [[Markov Decision Process (MDP)]] behind the environment.

#### Algorithm
**A. Description**
- Directly keep a running average of total [[state-value function (utility)]] at each state in different trials or [[episode (trajectory)]].  By the law of large number, the more observations we get for this value at state $s$, the closer it gets to the true expectation of the target value function at that state.

> Observation: We need to see **complete episodes** in order to get the true return at each state, which is infeasible with infinite process or offline learning (mostly).

**Note 1**: For each state, we can either consider its first appearance (result in *First-visit MC policy evaluation*) or its every appearance (result in *Every-visit MC policy evaluation*) in tracking.

**Note 2**: For [[action-value function (Q-function)]], we will consider (state, action) pairs instead of state.
> Application: In [[Model-Free Policy Iteration (Model-Free Value-based RL)]], we will take greedy actions with respect to [[action-value function (Q-function)]] instead of [[state-value function (utility)]] because we do not have $P^a_{ss^\prime}$.

**Note 3**: Mean tracking can be done online with incremental method, see below.

**B. Pseudocode**
![500](../resources/MCPrediction.png)

**C. Online Implementation**

Recall that mean at $k$-th timestep can be written with respect to $k-1$-th timestep as follows
$$
\begin{align}
\mu_k = \frac{1}{k} \sum_{i=1}^k x_i 
&= \frac{1}{k} \left( x_k + \sum_{i=1}^{k-1} x_i \right) \\
&= \frac{1}{k} x_k + \frac{1}{k} (k-1) \mu_{k-1} \\
&= \underbrace{\mu_{k-1}}_\text{previous mean} + \frac{1}{k} \underbrace{(x_k - \mu_{k-1})}_\text{error term}
\end{align}$$

Easily, we get the incremental implementation for value function
$$V(S_t) \leftarrow V(S_t) + \frac{1}{N(S_t)}(G_t - V(S_t))$$
where $N(S_t)$ is frequency of current state and $G_t$ is newly-observed return of that state.

**D. Decay Implementation**

We use step size $\alpha$ to (exponentially) forget past observations, which is useful in non-stationary problem with changes of real value function over time.
$$V(S_t) \leftarrow V(S_t) + \alpha(G_t - V(S_t))$$

An alternative way to see the above update is
$$V(S_t) \leftarrow (1 - \alpha) V(S_t) + \alpha G_t$$

**Disadvantage**:
- Violate the nature of states, or [[Bellman equation]]: states are not independent from each other -> slow converge

---
### FAQ

Q: How to design step size $\alpha$?
A: $\alpha$ is chosen as a function of number of visited state to ensure convergence to the correct value, i.e. $\alpha = f(n) = \frac{60}{59 + n}$ [0]

### References
[0] Artificial Intelligence: A Modern Approach

---
### FAQ

Q: How to design step size $\alpha$?
A: $\alpha$ is chosen as a function of number of visited state to ensure convergence to the correct value, i.e. $\alpha = f(n) = \frac{60}{59 + n}$ [0]

### References
[0] Artificial Intelligence: A Modern Approach