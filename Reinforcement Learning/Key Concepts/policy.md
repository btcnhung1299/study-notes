Policy is a function mapping a [[State in environment viewpoint, Observation in agent viewpoint]] to an action (deterministic) or the probability of an action (stochastic).

- Deterministic: $\pi(s) = a$
- Stochastic: $\pi(a \mid s) = \Pr_{\pi}[A=a, S=s]$
- Parametric stochastic (specifically in Deep RL): $\pi_{\theta}(a \mid s)$

Intuitively, it denotes which or how likely an action $a$ should be taken given a current state $s$.

## Optimal Policy
The optimal policy is the policy that gives maximum [[Value Function]].

It is proven that starting from the initial state, we can obtain optimal policy by greedily following (optimal) action $a$ such that the expected return over all courses of states reached from $s$ via $a$ is maximized (see proof in [[Policy Evaluation]]).
$$\begin{align}
\pi^{*}(s) &= \arg \max_{\pi} V^{\pi}(s) \\
&= \arg \max_{a} \sum_{s^{\prime}} P(s^{\prime} \mid s, a) V(s^{\prime})
\end{align}
$$

---
# FAQ
1. Q: How do we interpret an equation with and without policy (e.g. [[Bellman Equation]] for state-value with policy $V_{\pi}$ and without policy $V$?
	A: In equation without policy, we consider all actions demonstrated from the dataset; whereas in equation with policy, we consider actions **according to the specified policy $\pi$**.