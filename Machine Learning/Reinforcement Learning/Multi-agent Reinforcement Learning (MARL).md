Typical paradigm: centralised learning, decentralised execution
Issues:
- Multi-agent credit assignment: claim credits of each agent in the global reward; which cannot encourage agent to sacrifice for the common good
- Non-stationary transition dynamic
- Markov game
- Nash equilibrium

- Most deep MARL concerns fully cooporative or zero-sum/competitive settings.

## Non-stationary transition dynamics

We start by deriving [[Bellman equation]] in fully-observable [[Markov Decision Process (MDP)]] and proceed to partially-observable case. The later is more realistic as agents only obtain their own observations $o_i$ rather than the full state $s$ in the common centralised training decentralised execution settings.

1. **Fully-observable MDP (FOMDP)**: the Bellman optimality equation for a single agent $a$ given the policies of other agents
	$$Q^*(s, u_a | \pi_{-a}) 
	= \sum_{\mathbf{u}_{-a}} \pi_{-a}(\mathbf{u}_{-a} |s) 
	\left[ r + \gamma \sum_{s^\prime} P(s^\prime | s, \underbrace{u_a, \mathbf{u}_{-a}}_{\mathbf{u}}) 
	\max_{u^\prime_a} Q^*_a(s^\prime, u^\prime_a) \right]$$

	The term $\pi_{-a}(\mathbf{u}_{-a}|s)$ accounts for the non-stationary because it changes when the policies of other agents evolve over time.
	
	2. **Partially-observable MDP (POMDP)**: