Gamma function is proposed to rigorously formulate factorial with any positive number, e.g. $(\frac{4}{5})!$, which is infeasible with common form $n! = n \times (n-1) \times \dots \times 1$.

Gamma function is defined by
$$\Gamma(z) = \int_0^\infty x^{z-1} e^{-x} \,dx$$

It serves as alternative representation for factorial as it satisfies $n! = n(n-1)!$ (see [Proof](#proof))
$$\Gamma(n+1) = n!$$
e.g. $\Gamma(3) = 2!$

## Proof
Prove that $n! = n(n+1)!$ or $\Gamma(z+1) = z \Gamma(z)$.

Apply [[Integration by Parts]] to $\Gamma(z+1) = \int_0^\infty x^{z} e^{-x} \,dx = \int_0^\infty u \,dv$ where
$$\begin{align}
u = x^z &; u^\prime = zx^{z-1} \,dx \\
dv = e^{-x} \,dx &; v = -e^{-x}
\end{align}$$

$$\Gamma(z+1) = \underbrace{-x^z e^{-x} \Big|_0^\infty}_0 + z\int_0^\infty  x^{z-1} e^{-x} \,dx = z \Gamma(z)$$