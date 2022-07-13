1. [[#Components|Components]]
1. [[#Flow|Flow]]
1. [[#Novelty|Novelty]]
1. [[#Experimental settings|Experimental settings]]


# Abstract
QPLEX is a multi-agent reinforcement learning algorithm that employs centralised training, decentralised execution paradigm. Specifically, it uses the duplex dueling network introduced in [[Dueling Network]] to factorise the joint value function. The algorithm is claimed to achieve a complete IGM function class, introduce improvements over approximating method in [[QTRAN (Q Transformation)]] without structural constraints in [[VDN (Value Decomposition Network)]] or [[QMIX (Q Mixing)]].

# Description
## Components
- Individual action-value function $Q_i(\tau_i, \cdot)$
- Duplex dueling network that consists of 2 modules:
	- Transformation network that transforms $V_i, A_i$ conditioned on local observations $\tau_i$ to global $\boldsymbol{\tau}$
	- Dueling mixing that outputs $Q_{tot}$ by mixing $V_i(\boldsymbol{\tau})$ and $A_i(\boldsymbol{\tau}, \cdot)$

## Flow
![600](QPLEX.PNG)
- Given individual action values $Q_i(\tau_i, \cdot)$ (see step 1. in [[QMIX (Q Mixing)]]), the duplex dueling first computes $[V_i(\tau_i) = \max_{} Q_i(\tau_i, \cdot)$ then $A_i(\tau_i, \cdot) = Q_i(\tau_i, \cdot) - V_i(\tau_i)]$.  
- Transformation network takes current timestep $V_i(\tau_i), A_i(\tau_i, \cdot)$ and transform to the overall values $V_i(\boldsymbol{\tau})$ and $A_i(\boldsymbol{\tau}, \cdot)$ with positive linear combination (i.e. $w_i(\boldsymbol{\tau}) > 0$) **to ensure greedy consistency**
  $$V_i(\boldsymbol{\tau}) = w_i(\boldsymbol{\tau}) V_i(\tau_i) + b_i(\boldsymbol{\tau})$$$$A_i(\boldsymbol{\tau}, a_i) = w_i(\boldsymbol{\tau}) A_i(\tau_i, a_i)$$
  - From individual global values $V_i(\boldsymbol{\tau})$ and $A_i(\boldsymbol{\tau})$, the dueling mixing creates the mixed global values $V_{tot}(\boldsymbol{\tau})$ and $A_{tot}(\boldsymbol{\tau}, \boldsymbol{a})$
    $$V_{tot}(\boldsymbol{\tau}) = \sum_{i=1}^n V_i(\boldsymbol{\tau})$$$$A_{tot}(\boldsymbol{\tau}, \boldsymbol{a}) = \sum_{i=1}^n \lambda_i(\boldsymbol{\tau}, \boldsymbol{a}) A_i(\boldsymbol{\tau}, a_i)$$
    in which the constraints $\lambda_i(\boldsymbol{\tau}, \boldsymbol{a})$ is learnable such that $A_{tot}(\boldsymbol{\tau}, \boldsymbol{a}^*) = 0$ (see [Novelty](#novelty)). Given $V_{tot}(\boldsymbol{\tau})$ and $A_{tot}(\boldsymbol{\tau}, \boldsymbol{a})$, $Q_{tot}$ can be reformulated as follows
    $$\begin{align}
    Q_{tot}(\boldsymbol{\tau}, \boldsymbol{a}) 
    &= V_{tot}(\boldsymbol{\tau}) + A_{tot}(\boldsymbol{\tau}, \boldsymbol{a}) \\
    &= \sum_{i=1}^n [Q_i(\boldsymbol{\tau}, a_i) - A_i(\boldsymbol{\tau}, a_i)] + \sum_{i=1}^n \lambda_i(\boldsymbol{\tau}, \boldsymbol{a}) A_i(\boldsymbol{\tau}, a_i)] \\
    &= \sum_{i=1}^n Q_i(\boldsymbol{\tau}, a_i) + \sum_{i=1}^n (\lambda_i(\boldsymbol{\tau}, \boldsymbol{a}) - 1) A_i(\boldsymbol{\tau}, a_i)
  \end{align}$$

## Novelty
- The necessary conditions of [[IGM (Individual-Global-Max)]] often be relaxed or approximated in previous methods. QPLEX, on the other hand, is claimed to achieve complete IGM function class. In fact, the algorithm **guarantees the advantage-based IGM** that is basically equivalent to regular IGM:
  $$\arg \max_{\boldsymbol{a}} A_{tot}(\boldsymbol{\tau}, \boldsymbol{a}) = 
\begin{pmatrix}
\arg \max_{a_1} A_1(\tau_1, a_1) \\
\vdots \\ 
\arg \max_{a_n} A_n(\tau_n, a_n) \\
\end{pmatrix}$$
- In advantage-based IGM, given the optimal actions vector $\boldsymbol{a^*} = \{a_i^*\}_{i=1}^n$ , $V_{tot}^*(\boldsymbol{\tau}) = \max_{\boldsymbol{a}} Q_{tot}(\boldsymbol{\tau}, \boldsymbol{a})$, the [[Advantage function]] must satisfy
  $$A_{tot}(\boldsymbol{\tau}, \boldsymbol{a^*}) = A_i(\tau_i, a_i^*) = 0$$
  This transformation shows that instead of greedy consistency, we can **simply limit the value range of advantage functions $A_i$ to ensure advantage-based IGM**.

- When expressed with advantage function $A_{tot}(\boldsymbol{\tau}, \boldsymbol{a})$, the global action value $Q_{tot}(\boldsymbol{\tau}, \boldsymbol{a})$ is decomposed into two parts
  $$Q_{tot}(\boldsymbol{\tau}, \boldsymbol{a}) = \sum_{i=1}^n Q_i(\boldsymbol{\tau}, a_i) + \boxed{\sum_{i=1}^n (\lambda_i(\boldsymbol{\tau}, \boldsymbol{a}) - 1) A_i(\boldsymbol{\tau}, a_i)}$$
  The second term corrects for the discrepancy and helps us realise the full power of factorisation.

## Experimental settings
- Agent action-value network $Q_i$: [[Recurrent Neural Network (RNN)]]
- To learn $\lambda$, the authors use scalable multi-head attention module
  $$\lambda_i(\boldsymbol{\tau}, \boldsymbol{a}) = \sum_{k=1}^K \lambda_{i,k}(\boldsymbol{\tau}, \boldsymbol{a}) \phi_{i,k}(\boldsymbol{\tau}) v_k(\boldsymbol{\tau})$$