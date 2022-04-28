**Description**: When the Markov assumption is made, we imply that the future $s_{t+1}$ is modeled independently from the past $s_{1, \dots, s-1}$ given the present $s_t$. In other words, $s_{t+1}$ and $s_{1, \dots, s_1}$ are conditional independent given $s_t$ (see [[Marginal, Joint, and Conditional Probabilities]]).

Notation: $(s_{t+1} \perp s_{1, 2, \dots, t-1}) \mid s_t$ [0]

**Extended version**: The *order* of the assumption denotes the number of past states the future is dependent on.
- First-order Markov assumption: depend on 0 past state, or only depend on current state
- N-order Markov assumption: depend on $N-1$ past states

Markov assumption is hold in [[Markov Chain]].

---
*References*:
[0] Murphy, Machine Learning: A Probabilistic Perspective