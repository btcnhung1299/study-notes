Probabilistic approaches are favoured in machine learning where the **uncertainty** plays a central role. 

## Fundamental ideas
Probabilistic ML tries to apply probability distribution over "uncertain unobserved quantities" in the model and how they relate to the data.

Compositional probability of multiple probability distributions can be modelled, for example, with graphical models as
+ Directed graphs, or Bayesian [belief] networks
+ Undirected graphs, or Markov network/random field
+ Mixed graphs

The probabilities, i.e. [[Marginal, Joint, and Conditional Probabilities]], can be manipulated by applying two fundamental rules in probability theory: the sum rule and the product rule (which further combined in [[Bayes' theorem]]).

## Application
Probabilistic approaches can be applied in scientific modelling, Bayesian optimisation, data compression, or automatic model discovery, to name a few.

## Challenges

Notably in probabilistic modelling, the marginalising is computationally exhausive (and somewhat solved with approximating methods such as [[Markov Chain Monte-Carlo]]).

Probabilistic models should be flexible enough to capture the data, which are typically approached with an "universal" variable.

# FAQ
1. *Q: What are types of uncertainty?*
	A: Uncertainty can come from:
	- Measurement noises: blurry images, wrong translations, etc.
	- Large search space: uncertainty in deciding which values of model parameters would best predict the new data
	- Modelling choice: uncertainty in choosing which types of model (model architecture, number of layers, etc.) are appropriate to express the data