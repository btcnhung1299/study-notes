**Description**: The conditional probability *distribution* of future states only depend on the present state (memoryless property of stochastic process).

**Extended description**: The present state might or might not include a part of the history, depending on the **order** of the Markov model. For example,
- First-order Markov model (depend only on the current state): $P(s_t|s_{t-1})$
- Second-order Markov model (depend on the current state and 1 preceding state): $P(s_t|s_{t-1}, s_{t-2}$)