#### Reward
Reward function $R$ predicts the next reward triggered by one action. Particularly, $R_t$ is said to be the reward at timestep $t$ for performing action $A_t = a$, given current state $S_t = s$ and arriving at the state $S_{t+1}$ (i.e. a non-terminal node in Markov process). Following equivalent notions are freqently used.
$$
\begin{gather}
R_t = R(S_t, A_t, S_{t+1}) = R(S_t, A_t) = R(S_t) \\
R: |\mathcal{S}| \times |\mathcal{A}| \times |\mathcal{S}| \rightarrow \mathbb{R}
\end{gather}
$$

> Application: Reward is a unit concept in [[return]].

**Formulation**:
$$\begin{align}
R_t &= \mathbb{E}[R_{t+1} \mid S_t=s, A_t=a] \\
&= \sum_{r} r \sum_{s^{\prime} \in \mathcal{S}} P(s^{\prime}, r \mid s,a)
\end{align}$$

