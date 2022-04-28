Probabilistic inference is a task of estimating the unknowns given the known variables.

Let $\mathbf{x}$ denote the set of random variables.
- $\mathbf{x} = \underbrace{\mathbf{x}_v}_{\text{visible variables}} \,\cup \underbrace{\mathbf{x}_h}_{\text{hidden variables}}$
- $\mathbf{x}_h = \underbrace{\mathbf{x}_q}_{\text{query variables}} \, \cup \underbrace{\mathbf{x}_n}_{\text{nuisance variables}}$

The probability of interest is computed by marginalisation
$$p(\mathbf{x}_q | \mathbf{x}_v) = \int p(\mathbf{x}_q | \mathbf{x}_n, \mathbf{x}_v) \,d \mathbf{x}_n$$