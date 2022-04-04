When applied [[Taylor series]] to approximate cost function, we have
- $f(a) \equiv J(\boldsymbol{\theta})$
- $f^\prime(a) = \mathbf{g}$  (vector gradient)
- $f''(a) = \mathbf{H}$ (Hessian matrix)

The approximated cost function is
$$J(\boldsymbol{\theta}) = J(\boldsymbol{\theta}_0) + \frac{1}{1!} (\boldsymbol{\theta} - \boldsymbol{\theta}_0)^{\intercal}\boldsymbol{g} + \frac{1}{2!}(\boldsymbol{\theta} - \boldsymbol{\theta}_0)^{\intercal}\boldsymbol{H}(\boldsymbol{\theta} - \boldsymbol{\theta}_0) + \dots$$