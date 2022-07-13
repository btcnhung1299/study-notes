Individual-Global-Max (IGM) refers to the situation when the local optimal actions selected from $Q_i(\tau_i, \cdot)$ are jointly optimal actions selected from $Q_{jt}(\tau, \cdot)$
$$\arg \max_{\boldsymbol{u}} Q_{jt}(\boldsymbol{\tau}, \boldsymbol{u}) = 
\begin{pmatrix}
\arg \max_{u_1} Q_1(\tau_1, u_1) \\
\vdots \\ 
\arg \max_{u_n} Q_n(\tau_n, u_n) \\
\end{pmatrix}$$
In other words, $Q_i$ satisfy IGM for $Q_{jt}$ under $\boldsymbol{\tau}$.