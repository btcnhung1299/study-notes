DFAC is a framework that allows factorize centralised value function to decentralised values in multi-agent reinforcement learning.

## Components
DFAC uses two main components to transform single-value $Q$ to distributional $Q$:
- Mean-shape decomposition: constrains the factorisation of expected value function
- Quantile mixture: constrains the factorisation of total return distribution 


## Novelty
- Instead of single-value $Q$, DFAC enforces distributional $Q$, resulted in distributional variants DVN (from VDN), QMIX (from DMIX).
- 