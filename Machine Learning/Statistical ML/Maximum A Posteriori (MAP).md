In [[Bayesian Learning]], we want to find parameter $\theta$ such that the posterior distribution $\pi(\theta | x)$ is maximised.
$$\hat{\theta} = \arg \max_\theta \frac{f(x|\theta) \pi(\theta)}{\int_\theta f(x | \theta) \pi(\theta)}$$

As the prior predictive distribution of $X$, i.e. $m(x) = \int_\theta f(x | \theta) \pi(\theta)$, is constant given our dataset, the optimisation remains maximising the posteriori in the numerator, namely **M**aximum **A** **P**osteriori (MAP)
$$\hat{\theta} = \arg \max_\theta f(x|\theta) \pi(\theta)$$
or equivalently,
$$\hat{\theta} = \arg \max_\theta \left[ \log f(x|\theta) + \log \pi(\theta) \right]$$