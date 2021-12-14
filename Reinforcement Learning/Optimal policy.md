Given $U^{\pi}$ is the utility for a policy $\pi$, we want to find the optimal policy whose utility is maximised:
$$\begin{align}
\pi^{*} &= \arg \max_{\pi} U^{\pi} \\
&= \arg \max_{a} \sum_{s^{\prime}} P(s^{\prime} \mid s, a) U(s^{\prime})
\end{align}
$$