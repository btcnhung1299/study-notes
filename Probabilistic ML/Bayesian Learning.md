Bayesian Learning is a learning paradigm that takes advantage of [[Bayes' theorem]] to infer the posterior distribution of parameters $\theta$ from observed data $X$. Particularly,
$$P(\theta \mid X) = \frac{\mathcal{L}(X \mid \theta) * P(\theta)}{\int_\theta \mathcal{L}(X \mid \theta) P(\theta) d\theta}$$
where
- $P(\theta)$ is prior distribution of $\theta$, or our "beliefs" of $\theta$ before seeing any data.
- $\mathcal{L}(X \mid \theta)$ is the likelihood function

The posterior probability acts as the prior probability in the next step of an iterative process to correct our beliefs. 

We can use this posterior to predict unseen data given our previous data, or do **Bayesian prediction**:
$$P(x_{\text{test}} \mid X) = \int_\theta P(x_{\text{test}} \mid \theta) P(\theta \mid X) d\theta$$