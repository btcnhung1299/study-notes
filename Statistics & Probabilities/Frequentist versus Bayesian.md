## Frequentist
**View on probabilities**: Classical statistics, or frequentist, sees probability as the frequency of an event, and thereby are limited to repeatable experiments (in which we can measure the frequency).

**View in machine learning**: Given a model $f$ with parameter $\theta$, frequentists believe $\theta$ is fixed but unknown and thereby the [[Likelihood]] $l(\theta \mid \mathbf{x})$ is defined by
$$l(\theta | \mathbf{x}) = f(\mathbf{x} | \theta) = \prod_{i} f(x_i \mid \theta)$$
while assume all the data points are i.i.d.

**Chi-Square Test** is the one powerful statistical devices that comes from frequentist.

## Bayesian
**View on probabilities**: Bayesian sees probability as the degree of belief.

**View in machine learning**: Bayesians model $\theta$ as random variables and apply prior distribution over $\theta$, denoted as $\pi(\theta)$, resulted in [[Bayesian Learning]]. The prior distribution is iteratively updated with new data point using [[Bayes' theorem]]:
$$\pi(\theta | x) 
= \frac{f(x | \theta) \pi(\theta)}{\int_\theta f(x \mid \theta) \pi(\theta) \,d\theta}$$

**Bayesian Decision Making** is the one powerful statistical devices that comes from Bayesian, which exhaustively applied in day-to-day lives to update our prior belief.