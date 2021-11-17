Original form:

$$f(x) = f(a) + \frac{1}{1!}f'(a)(x-a) + \frac{1}{2!}f''(a)(x-a)^2 + \dots$$

Applied to cost function:
$$J(\boldsymbol{\theta}) = J(\boldsymbol{\theta}_0) + \frac{1}{1!} (\boldsymbol{\theta} - \boldsymbol{\theta}_0)^{\intercal}\boldsymbol{g} + \frac{1}{2!}(\boldsymbol{\theta} - \boldsymbol{\theta}_0)^{\intercal}\boldsymbol{H}(\boldsymbol{\theta} - \boldsymbol{\theta}_0) + \dots$$

where $\boldsymbol{H}$ (Hessian matrix) is the second-order derivative of the cost function in [[Cost Function, Gradient, Jacobian, and Hessian]].