Variable elimination is an exact inference algorithm. It works by iteratively eliminate irrelevent variables to obtain the probability of interest $P(\underbrace{Q_1, ..., Q_m}_{\text{target variables}} \mid \underbrace{e_1, ..., e_n}_{\text{evident variables}})$.

## General Flow
1. Let $\mathcal{P}$ contain conditional distributions in the Bayesian network that involves evident variables.
	<sub>**Example**: the following Bayesian network  includes $\mathcal{P} = \{ P(U), P(V), P(W), P(X|U,V), P(Y|V,W), P(+z|X,Y) \}$. The query of interest is $P(U|+z)$.
	![150](./resources/VariableEliminationExample-BayesianNetwork.PNG)</sub>
2. For each variable $Y$ in all variables except target ones $\mathbf{Y} = \mathbf{X} \setminus \mathbf{X}_{\text{target}}$:
	<sub>**Example**: $Y \in \mathbf{Y} = \{ W,Y,V,X \}$</sub>
	1. Select all relevent conditional distributions $q := \prod_{p \in \mathcal{P}_Y} p$
		<sub>**Example**: $P(W)P(Y|V, W)$</sub>
	2. Represent this new distribution as a function of involved variables $r := \sum_y q$
		<sub>**Example**: $f_1(V,Y)=\sum_w P(w)P(Y|V,w)$</sub>
	3. Eliminate involved factors and add the newly reduced one $\mathcal{P} := \mathcal{P} \setminus \mathcal{P}_Y \cup \{r\}$
		<sub>**Example**: the Bayesian network left with $\mathcal{P} = \mathcal{P} \setminus \{ P(W), P(Y|V,W) \} \cup f_1(V,Y)$</sub>
3. After elimination of irrelevant variables, we can represent probability of interest as the product of remaining factors $p(\mathbf{X}_{\text{target}}) = \prod_{p \in \mathcal{P}} p$
	<sub>**Example**: $P(U|+z) = P(U) f_4(+z,U)$</sub>
4. Normalise $p(\mathbf{X_\text{target}})$ so that it satisfies the probabilitity property (i.e. sum to 1).
	<sub>**Example**: $P(U|+z) = \frac{P(U) f_4(+z,U)}{\int_u P(u) f_4(+z,u)}$</sub>

Note: see [1] for elaboration of given example :)

> Observation: If the elimination order is not carefully chosen, we might end up with very high complexity in step 2 of the algorithm. Imagine when we have the joint probability $f(U,V,X,Y)$ where each  variable is binary. Then, the total number of factors are $2^4=16$. The complexity raises exponentially in the case of such discrete variables.

---
[1] Pieter Abbeel, Variable Elimination, https://youtu.be/FDNB0A61PGE