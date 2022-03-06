Integral by parts is used to find integral of products.

$$\int_a^b u \,dv = uv \Big|_a^b - \int_a^b v \,du$$

**For example**, find $\int x \cos(x) \,dx$.

Let $\int x \cos(x) \,dx = \int u \,dv$, or
$$\begin{align}
u =x &; du = 1 \,dx \\
dv = \cos(x) \,dx &; v = \sin(x)
\end{align}$$

Hence, $\int x \cos(x) \,dx = x \sin(x) - \int \sin(x) \, dx = x \sin(x) + \cos(x) + C$