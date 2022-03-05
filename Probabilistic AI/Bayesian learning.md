We can use [[Bayes' theorem]] to infer causes from effects. Assume $A \implies B$ and we observe $B$ in real life, we want to know how likely $A$ is the cause of $B$. Analogy in machine learning would be how likely a model, parameterised by $\theta$, generates the observed data $D$:
$$P(\theta \mid D) = \frac{P(D \mid \theta) * P(\theta)}{P(D)}$$

The posterior probability acts as the prior probability in the next step of an iterative process to correct our beliefs. In the end, we can use the probability distribution to predict unseen data given our previous data:
$$P(D_{\text{test}} \mid D) = \int_\theta P(D_{\text{test}} \mid D, \theta) d ....$$