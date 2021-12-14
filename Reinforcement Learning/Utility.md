**Purpose**: 

**Definition**: The utility is defined to be the expected sum of discounted rewards if policy $\pi$ is followed from state $s$ onwards, or expected **reward-to-go**.
$$U^{\pi}(s) = \mathbb{E} \left[ \sum_{t=0}^{\infty} \gamma^{t} R(S_t) \right]$$
where $R$ is the reward function, $S_t$ is the state at timestep $t$ when executing policy $\pi$ ($S_0 = s$), and $0 < \gamma < 1$ is a [[Discount factor]].