## Reward
Reward at timestep $t$, denoted as $R_t$, corresponds to expected reward for performing action $A_t = a$ given current state $S_t = s$ and **arriving at a non-terminal state** $S_{t+1}$.
$$
\begin{gather}
R_t = R(S_t, A_t, S_{t+1}) = R(S_t, A_t) = R(S_t) \\
R: |\mathcal{S}| \times |\mathcal{A}| \times |\mathcal{S}| \rightarrow \mathbb{R}
\end{gather}
$$

and,
$$\begin{align}
R_t &= \mathbb{E}[R_{t+1} \mid S_t=s, A_t=a] \\
&= \sum_{r} r \sum_{s^{\prime} \in \mathcal{S}} P(s^{\prime}, r \mid s,a)
\end{align}$$

## Return

Return at timestep $t$, denoted as $G_t$ (abbreviated for "goal"), is the cumulative rewards from $t$ onwards. Typically, we consider the (infinite) discounted return with [[discount factor]] $\gamma$
$$G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}$$

Particularly, the finite discounted return over [[episode (trajectory)]] $\tau$ is written as
$$G(\tau) = \sum_{t=0}^{T} \gamma^t R_{t+1}$$

---
# FAQ

1. Q: Why discounted return is preferred over undiscounted return?
A: The discounted return has several desirable properties:
	- Intuitively, it illustrates the understandable preference of immediate rewards over future rewards as it is hard to have a perfect prediction over the long future (because [[A trivial difference can blow up into a chaos]])
	- Mathematically, it keeps the return bounded, i.e. the return will not be arbitrarily big, particularly when we fall into infinite loops with cyclic Markov process

2. Q: Why the timestep of return starts with $t+1$? If it demonstrates the cumulative rewards from $t$ onwards, it should start from $t$, doesn't it?
A: In fact, starting from $t$ is reasonable enough. However, if we consider the reward as an interaction of the environment to the agent right after we take the action $a_t$, then we might regard the reward as happened as in timestep $t+1$.