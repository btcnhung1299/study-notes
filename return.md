
#### Return
Return at timestep $t$ is the cumulative [[reward]]s from $t$ onwards. Typically, we consider the discounted return with [[discount factor]] $\gamma$ and use notation $G_t$, which stands for "goal", to denote return at timestep $t$.
$$G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}$$
- Finite-horizon discounted return over [[episode, or trajectory]] $\tau$ with horizontal size $T$
$$R(\tau) = \sum_{t=0}^{T} \gamma^t R_{t+1}$$

---
#### FAQ

1. Q: Why discounted return is preferred over undiscounted return?
A: The discounted return has several desirable properties:
	- Intuitively, it illustrates the understandable preference of immediate rewards over future rewards as it is hard to have a perfect prediction over the long future (because [[A trivial difference can blow up into a chaos]])
	- Mathematically, it keeps the return bounded, i.e. the return will not be arbitrarily big, particularly when we fall into infinite loops with cyclic Markov process

2. Q: Why the timestep of return starts with $t+1$? If it demonstrates the cumulative rewards from $t$ onwards, it should start from $t$, doesn't it?
A: In fact, starting from $t$ is reasonable enough. However, if we consider the reward as an interaction of the environment to the agent right after we take the action $a_t$, then we might regard the reward as happened as in timestep $t+1$