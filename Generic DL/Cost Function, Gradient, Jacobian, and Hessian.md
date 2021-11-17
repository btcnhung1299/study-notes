**Cost Function**
- Denoted as $J(\boldsymbol{\theta})$
- $J: \mathbb{R}^n \rightarrow \mathbb{R}$
- Mapping from parameters $\boldsymbol{\theta}$ to real value, or error

**Gradient**
- Denoted as $\boldsymbol{g} = \nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta})$
- $\boldsymbol{g}: \mathbb{R}^n \rightarrow \mathbb{R}^n$ where $g_i = \frac{\delta}{\delta \theta_i} J(\boldsymbol{\theta})$
- Mapping from $\theta_i$ to its partial derivative

**Jacobian**
- Denoted as $F(\boldsymbol{\theta})$
- $F: \mathbb{R}^n \rightarrow \mathbb{R}^{m \times n}$
- $\begin{bmatrix} \nabla_{\boldsymbol{\theta}} f_1(\boldsymbol{\theta}) \\ ... \\ \nabla_{\boldsymbol{\theta}} f_m(\boldsymbol{\theta}) \end{bmatrix}$
- Stacking gradients of different function

**Hessian**
- Denoted as $\boldsymbol{H}$
- $H: \mathbb{R}^n \rightarrow \mathbb{R}^{n \times n}$ where $H_{i,j} = \frac{\delta}{\delta \theta_j}g_i = \frac{\delta}{\delta \theta_j \theta_i} J(\boldsymbol{\theta})$

*Hessian is the Jacobian matrix with functions are the (cost function's) gradient components*