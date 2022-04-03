A policy is guaranteed to converge to optimal policy if it is *GLIE* (**G**reedy in the **L**imit of **I**nfinite **E**xploration), i.e. it satisfies 2 conditions:
1. All (state, action) pairs are explored infinitely many times, which means all states must be covered.
	$$\lim_{k \to \infty} N_k(s,a) \to \infty$$
2. The policy (eventually) converges to a greedy policy, i.e. the probability converges to 1 for greedy action. It is required to satisfy [[Bellman equation]].
	$$\lim_{k \to \infty} \pi_k(a \mid s) = \mathbf{1}(a = \arg \max_{a^\prime \in \mathcal{A}} Q_k(s, a^\prime))$$
	
	
*Example*: $\epsilon$-greedy (used in [[Model-Free Policy Iteration (Model-Free Value-based RL)]]) is GLIE when $\epsilon$ decays towards 0, i.e. picking random actions and proven to improve current policy.