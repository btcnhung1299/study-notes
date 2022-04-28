Bayesian learning is a learning paradigm that takes advantage of [[Bayes' theorem]] to infer the posterior distribution of parameters $\theta$ from observed data $X$.

## General approach
Given
- $\pi(\theta)$ as the prior distribution of $\theta$
- $f(x | \theta)$, or $\mathcal{L}(\theta | x)$, as likelihood function
- $\psi(x, \theta) = f(x|\theta) \pi(\theta)$ as joint distribution of $(X ,\theta)$
- $m(x) = \int_\theta \psi(x, \theta) \,d\theta = \int_\theta f(x | \theta) \pi(\theta)$ as prior predictive distribution of $X$

We can derive the posterior distribution of $\theta$ with Bayes' theorem
$$\pi(\theta | x) = 
\frac{f(x | \theta) \pi(\theta)}{m(x)}$$

The posterior probability $\pi(\theta|x)$ acts as the prior probability $\pi(\theta)$ in the next step of an iterative process to correct our beliefs. Finally, we can use this posterior to predict unseen data given our previous data:
$$\begin{align}
f(x_{n+1} \mid \mathbf{x}) 
&= \int_\theta f(x_{n+1} | \theta, \mathbf{x}) \pi(\theta | \mathbf{x}) \,d\theta \\
&= \int_\theta f(x_{n+1} | \theta) \pi(\theta | \mathbf{x}) \,d\theta \tag{X are i.i.d}
\end{align}$$