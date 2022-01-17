#### Description

Policy is a function mapping an observation (typically and misleadingly referred as state) to an action or the probability of an action. Intuitively, it denotes which or how likely an action $a$ should be taken given a current state $s$.

#### Policy representation
- Deterministic: $\pi(s) = a$
- Stochastic: $\pi(a \mid s) = \Pr_{\pi}[A=a, S=s]$

> In Deep RL, we model the policy by a neural network with parameters $\theta$ whose input has *the dimension of observation* and *output has the dimension of action*. The parameterized policy is denoted as $\pi_{\theta}(a \mid s)$.

#### Optimal Policy
The optimal policy is the policy that gives maximum [[value function]].

It is proven that starting from the initial state, we can obtain optimal policy by greedily following (optimal) action $a$ such that the expected return over all courses of states reached from $s$ via $a$ is maximized.
$$\begin{align}
\pi^{*}(s) &= \arg \max_{\pi} V^{\pi}(s) \\
&= \arg \max_{a} \sum_{s^{\prime}} P(s^{\prime} \mid s, a) V(s^{\prime})
\end{align}
$$

---
#### FAQ
1. Q: How do we interpret an equation with and without policy (e.g. [[Bellman equation]] for state-value with policy $V_{\pi}$ and without policy $V$?
	A: In equation without policy, we consider all actions demonstrated from the dataset; whereas in equation with policy, we consider actions **according to the specified policy $\pi$**.