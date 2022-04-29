MABCQ, or **M**ulti-agent **B**atch **C**onstraint **Q**-learning [1] is a offline, fully decentralised multi-agent reinforcement learning algorithm. MABCQ addresses extrapolation error and miscoordination using value deviation and transition normalisation.

## Components
MABCQ contains all components in [[BCQ (Batch-Constrained Q-learning)]] and the additional weight factors:
- Value deviation factor
- Transition normalisation factor

## Flow

## Novelty
<sub>There are two main problems in offline, fully decentralised multi-agent reinforcement learning. The first one is extrapolation error, which refers to the mismatch in value estimation between learnt and behaviour policies. The problem is ubiquitous in offline learning. The later is miscoordination among agents, which happens because each agent is blinded from the transition dynamics learnt by the others, and thereby acts suboptimally with respect to others.</sub>

1. Because offline demonstrations aren't expert (most of the time), we likely underestimate values of good actions. Particularly, $P_{\mathcal{B}_i}$ induced in behaviour policies are (expected to be) smaller than $P_{E_i}$ in learnt policies as all agents strive for optimal actions (so they give high values for good actions). Hence, the authors suggest correction of $P_{\mathcal{B}_i}$ to be optimistic towards each agent (assume optimal values are selected)
	$$P_{\mathcal{B}_i}(s^\prime \mid s, a) 
	* \left( 1 + \frac{V_i^*(s^\prime) - \mathbb{E}_{\hat{s}^\prime}[V_i^*(\hat{s}^\prime)]}{|\mathbb{E}_{\hat{s}^\prime}[V_i^*(\hat{s}^\prime)]|} \right)$$
	Note: normalisation is followed so that $\sum_i P_{\mathcal{B_i}} = 1$.

## Experimental setting


# FAQ
1. How does value deviation design and why?