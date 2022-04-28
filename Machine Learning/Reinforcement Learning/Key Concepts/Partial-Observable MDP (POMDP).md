Partial-observable MDP (POMDP) assumes the underlying [[Markov Decision Process (MDP)]]. However, agents in POMDP cannot observe the underlying states but its observations, hence "partial-observable" (see [[state (in env) or observation (in agent)]]).

A POMDP can be described by a 7-element tuple
$$\langle \mathcal{S}, \mathcal{A}, R, T, \Omega, O, \gamma \rangle$$

The notations are almost similar to [[Markov Decision Process (MDP)]]'s with several modifications:
- $T$ is the transition probability function (denoted by $P$ in MDP)
- $\Omega$ is the **observation** space
- $O: \mathcal{S} \rightarrow \Omega$ is the **observation function**


# FAQ
1. **Q**: Why both observation space $\Omega$ and observation function $O$ are needed to specify a POMDP?
	**A**: Because there are different ways to obtain observations in $\Omega$?
	
	