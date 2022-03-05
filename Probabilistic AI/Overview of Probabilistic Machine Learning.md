Probabilistic approaches are favoured in machine learning where the **uncertainty** plays a central role. 

## Fundamental ideas
Probabilistic ML tries to apply probability distribution over "uncertain unobserved quantities" in the model and how they relate to the data.

Compositional probability of multiple probability distributions can be modelled, for example, with graphical models as
+ Directed graphs, or Bayesian [belief] networks
+ Undirected graphs, or Markov network/random field
+ Mixed graphs

The probabilities, i.e. [[Marginal, Joint, and Conditional Probabilities]], can be manipulated by applying two fundamental rules in probability theory: the sum rule and the product rule (which further combined in [[Bayes' theorem]]).

## Uncertainty
Uncertainty can come from:
- Measurement noises: blurry images, wrong translations, etc.
- Large search space: in deciding which values of model parameters that best predict the new data
- Modelling choice: in deciding which types of model are appropriate to express the data: model architectures, number of layers

## Application
Probabilistic approaches can be applied in scientific modelling (to model uncertainty), Bayesian optimisation, data compression, and automatic model discovery.

### Challenges
- Scientific modelling: computationally exhaustive (because of marginalising); must be flexible enough (frequently by including a "universal" variable)
-  