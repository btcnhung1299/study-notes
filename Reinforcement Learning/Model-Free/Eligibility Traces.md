Eligibility traces is a basic mechanism that is frequently combined in [[Temporal-Difference (TD) Policy Iteration]] to produce a general method.

The eligibility traces can be applied in forward view TD and backward view TD.

**A. In Forward View TD**

In this view, eligibility traces act as a bridge/compromise between [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]] and [[Temporal-Difference (TD) Policy Evaluation]].

- Let $\tilde{G}_t^{(n)}$ denote the (estimated) n-step return, i.e. the return that includes $n$ first rewards and approximation after that.
$$\tilde{G}_t^{(n)} = R_{t+1} + \gamma R_{t+2} + ... + \gamma^{n-1} R_{t+n} + \gamma^n \tilde{V}(S_{t+n})$$
> Observation: When $n = \infty$, $G_t^{(n)}$ is the same in [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]].

- The $\lambda$-return combines **all** n-step returns, where $\lambda$ is an eligibility trace. In general, TD(λ) replaces $\tilde{G}_t$ by $\tilde{G}_t^\lambda$
$$\tilde{G}_t^\lambda = (1-\lambda) \sum_{n=1}^\infty \lambda^{n-1} \tilde{G}_t^{(n)}$$
which gives rise to the following update
$$V(S_t) \leftarrow V(S_t) + \alpha( \tilde{G}_t^\lambda - V(S_t) )$$

![330](ForwardView_EligibilityTraces.png)

**B. In Backward View TD**

In this view, eligibility traces act as a mechanism to give credits to previous actions with respect to their frequency and recency.

- Let $E_t(s)$ denote the eligibility trace, or the weight associated with a state at given timestep $t$. Each $E_t(s,a)$ is a function that decays previous result and increases frequency of that state happening.
$$\begin{align}
E_0(s) &= 0 \\
E_t(s) &= \gamma \lambda E_{t-1}(s) + \mathbf{1}(S_t=s)
\end{align}$$

- The final update
$$V(S_t) \leftarrow V(S_t) + \alpha E_t(s) \underbrace{(\tilde{G}_t - V(S_t))}_{\delta_t}$$
where $\tilde{G}_t = R_{t+1} + \gamma V(S_{t+1})$ is boostrapped return in [[Temporal-Difference (TD) Policy Evaluation]].

![330](BackwardView_EligibilityTraces.png)