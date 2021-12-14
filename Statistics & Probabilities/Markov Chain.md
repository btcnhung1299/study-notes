**Description**: A system that holds [[Markov assumption]] will have the joint distribution of $s_1, \dots, s_n$ (see [[Marginal, Joint, and Conditional Probabilities]]) given as follows:
$$
\begin{align}
p(s_1, \dots, s_n) \stackrel{\text{Chain Rule}}{=} &p(s_1) \prod_{t=2}^{n} p(s_t \mid s_1, \dots, s_{t-1}) \\ \stackrel{\text{Markov assumption}}{=} &p(s_1) \prod_{t=2}^{n} p(s_t \mid s_{t-1}) \tag{1}
\end{align}
$$

**Extended version**: The $n$-th order [[Markov assumption]] results in the $n$-th order Markov Chain whose future state depends on $n-1$ past states.

Application: n-gram [[Language Model]]

**Components**: From equation (1), a Markov chain is characterised by two components:
- Initial distribution $p(s_1)$
- State transition matrix $p(s_t = j \mid s_{t-1} = i)$
