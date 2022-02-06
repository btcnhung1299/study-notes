## $\epsilon$-greedy

In $\epsilon$-greedy, we randomly take greedy actions or exploratory actions. The policy obtained via $\epsilon$-greedy improvement is called $\epsilon$-soft policy.
	$$\pi_t(a \mid s) = 
	\begin{cases}
		1 - \epsilon + \frac{\epsilon}{|\mathcal{A}|}, &\text{if } a^* = \arg \max_{a \in \mathcal{A}} Q(s, a) \\
		\frac{\epsilon}{|\mathcal{A}|}, &\text{otherwise}
	\end{cases}
	$$

We can prove that $\epsilon$-soft policy is improved over current policy (see [Proof](#proof)).

### Proof

Prove that the policy $\pi^\prime$ by acting with respect to $\epsilon$-greedy result in policy improvement over current policy $\pi$, i.e. $V_{\pi^\prime}(s) \geq V_\pi(s)$.

- The $\epsilon$-greedy gives
	$$\begin{align}
	Q_\pi(s, \pi^\prime(s)) &= \sum_{a \in \mathcal{A}} \pi^\prime(a \mid s) Q_\pi(s, a) \\
	&= \frac{\epsilon}{|\mathcal{A}|} \sum_{a \in \mathcal{A}} Q_\pi(s, a) + \left[ 1 - \epsilon + \frac{\epsilon}{|\mathcal{A}|} \right] \arg \max_{a \in \mathcal{A}} Q_\pi(s,a)
	\end{align}$$
- It is easy to see that the maximum value is always greater or equal than the ...


---
# FAQ

1. Q: Why the probability for random actions to be $\frac{\epsilon}{|\mathcal{A}|}$ and not $\epsilon$?
	A: At a timestep, the probability of an greedy action to be taken is $1 - \epsilon$, which means other random actions is taken with $\epsilon$ probabilities.
	We have $|\mathcal{A}|$ actions to can be selected randomly from (not excluding the greedy action). Assume uniform distribution in selection, each action will be picked with $\frac{\epsilon}{|\mathcal{A}|}$.
	In other words, the total probability for greedy action, taken into account that it can be picked in random selection, is $1 - \epsilon + \frac{\epsilon}{|\mathcal{A}|}$.