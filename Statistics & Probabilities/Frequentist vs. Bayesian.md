Let consider a model $f$ parameterised by $\theta$.

## Frequentist
Classical statistics, or frequentist, sees probability as the frequency of an event, and thereby are limited to repeatable experiments (?).

Frequentists believe $\theta$ is fixed but unknown and the likelihood $l(\theta \mid \mathbf{x})$, i.e. the probability that current data set corresponds to the parameter $\theta$, is given by:
$$l(\theta \mid \mathbf{x}) = f(\mathbf{x} \mid \theta) = \prod_{i} f(x_i \mid \theta)$$
with the assumption that all the data points are iid.

**Chi-Square Test** is the one powerful statistical devices that comes from frequentist.

## Bayesian
Bayesian sees probability as the degree of belief.

Bayesians believe $\theta$ is a random variable. Hence, Bayesian applies prior distribution over $\theta$, denoted as $\pi(\theta)$.

The prior distribution is then gets updated when new data is observed via [[Bayes' theorem]]:
$$\pi(\theta \mid x) 
= \frac{f(x \mid \theta) \pi(\theta)}{m(x)} 
= \frac{f(x \mid \theta) \pi(\theta)}{\int_\theta f(x \mid \theta) \pi(\theta) d\theta}$$

**Bayesian Decision Making** is the one powerful statistical devices that comes from Bayesian, which exhaustively applied in day-to-day lives to update our prior belief.