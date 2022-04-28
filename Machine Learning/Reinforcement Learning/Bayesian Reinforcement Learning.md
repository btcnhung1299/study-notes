**Background**: Choose optimal policy with respect to the estimated model is not a good idea.
For example: "a taxi agent might ignore red lights once or twice without ill effects and formulate the policy to ignore red lights"

**Purpose**: Inject our prior beliefs in the true transition model

**Formulation**: Choose the utility function that gives the highest expected utility, given the posterior hypothesis $P(h \mid \mathbf{e})$ of our belief $P(h)$, or obtained transition model, with the evidence during observed states $\mathbf{e}$
$$\pi^{*} = \arg \max_{\pi} \sum_{h} P(h \mid \mathbf{e}) u^{\pi}_h$$
where $u^{\pi}_h$ is expected utility (averaged over all possible states) when executing policy $pi$ with transition model $h$.