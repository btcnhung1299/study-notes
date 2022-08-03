Example: Given an exponential distribution with p.d.f $f(x) = e^{-x}$. Then, the c.d.f (cumulative distribution function) is $F(x) = \int_{-\infty}^{x} e^{-t} \,dt = 1 - e^{-x}$ . We can find the inverse c.d.f by solving for $x$, given $F(x) = u$. Hence, the inverse c.d.f is $x = -\log(1 - u)$.

### Application
Inverse CDF sampling technique (inverse transformation) can be used to generate sample from a distribution.