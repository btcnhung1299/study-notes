**Purpose**: Learn the [[State-value Function, or Utility]] $U$

**Idea**: Keep track of running statistics of transition probability and use algorithms (e.g. Policy Evaluation) to solve [[Bellman Equation]] with the observations.
*In other words*, we want to maximize the likelihood given observed transition probability and rewards.

**Materials**:
- Input: (current state $s^{\prime}$, corresponding reward $r^{\prime}$)
- Output: next state
- Updatable global variables: [[State-value Function, or Utility]] $U$, transition probability $P$, and rewards $R$
- Global variables: policy $\pi$

*Note*:
- Passive RL: $\pi$ is fixed
- Active RL: $\pi$ is designed to combine exploitation and exploration (e.g. GLIE)

**Procedure**:
For a newly-reached state $s^{\prime}$ which is the result of the action $a$ performed on previous state $s$:
1. If we do not have prior knowledge about reward at $s^{\prime}$, then update it by the observed reward $r^{\prime}$
2. Keep track of the total times we obtain $s^{\prime}$ given $(s, a)$, or $N_{s^{\prime} \mid s,a}$ as well as the total times we observe $(s, a)$, or $N_{s,a}$
3. Update the related transition probability $P(t \mid s, a)$ where $t$ is any state that can obtained from $s, a$
4. Update [[State-value Function, or Utility]] $U$ by solving [[Bellman Equation]] (e.g. using Policy Evaluation)
5. Repeat the process with the next state $s \leftarrow s^{\prime}, a \leftarrow \pi(s^{\prime})$

*Note*: Basically, we are performing [[Maximum Likelihood Estimate (MLE)]] to learn the transition model [0]

**Disadvantage**:
- Intracable for large state spaces: as they need to learn transition probability given all state combinations


#### References:
[0] Artificial Intelligence: A Modern Approach