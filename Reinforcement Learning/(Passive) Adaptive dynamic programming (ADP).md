**Procedure**:
- Input: (current state $s^{\prime}$, corresponding reward $r^{\prime}$)
- Output: next state
- Updatable global variables: utility function $U$, transition probability $P$, and rewards $P$
- Fixed variable: policy $\pi$

For a newly-reached state $s^{\prime}$ which is the result of the action $a$ performed on previous state $s$:
1. If we do not have prior knowledge about reward at $s^{\prime}$, then update it by the observed reward $r^{\prime}$
2. Increase the total times we obtain $s^{\prime}$ given $(s, a)$, $N_{s^{\prime} \mid s,a}$ as well as the total times we observe $(s, a)$, $N_{s,a}$
3. Update the related transition probability $P(t \mid s, a)$
4. Update [[Utility]] function $U$ by solving fixed-policy [[Bellman equation]] (using Policy Evaluation, for example)
5. Recursively go to the next state $s \leftarrow s^{\prime}, a \leftarrow \pi(s^{\prime})$

*Note*: Basically, we are performing [[Maximum Likelihood Estimate]] to learn the transition model [0]

**Disadvantage**:
- Intracable for large state spaces: as they need to learn transition probability given all state combinations

---
*References*:
[0] Artificial Intelligence: A Modern Approach