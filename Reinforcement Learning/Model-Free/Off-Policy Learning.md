### Description

Off-policy refers to the situation when the [[Policy]] we are following is different than the one we are learning from.

Formally, the policy in our dataset (that generates behavior) is called *behavior policy*, denoted as $\mu(a \mid s)$, whereas the policy we are following is $\pi(a \mid s)$. Assume $\mu \neq \pi$.

### Importance Sampling for Off-policy prediction

[[Importance Sampling]] is widely used to utilize the knowledge we learned from behavior policy $\mu$ to estimate expected return given the current policy $\pi$.

**A. In [[Monte-Carlo (MC) Policy Evaluation, or Direct Utility Estimate]]**

- Let $G_t^\mu$ denote return obtained by following a sequence of (state, action) pairs $(S_k, A_k)_{k \geq t}$ under policy $\mu$. Hence, the probability to reach return $G_t^\mu$ is given by
	$$\prod_{k \geq t} \mu(A_k \mid S_k) * p_\mu(S_{k+1} \mid S_k, A_k)$$
	
	Similarly, the probability to reach return $G_t^\pi$ **given transition probability learned from behavior policy $p_\mu$** is
	$$\prod_{k \geq t} \pi(A_k \mid S_k) * p_\mu(S_{k+1} \mid S_k, A_k)$$
	
- Hence, the return $G_t^{\pi/\mu}$ is obtained from $G_t^\mu$ with the importance-sampling ratio as below
 $$\begin{align}
 G_t^{\pi/\mu} 
 &= \frac{\prod_{k \geq t} \pi(A_k \mid S_k) * p_\mu(S_{k+1} \mid S_k, A_k)}{\prod_{k \geq t} \mu(A_k \mid S_k) * p(S_{k+1} \mid S_k, A_k)} G_t^\mu \\
 &= \frac{\prod_{k \geq t} \pi(A_k \mid S_k)}{\prod_{k \geq t} \mu(A_k \mid S_k)} G_t^\mu
 \end{align}$$
 
 > Observation: The importance-sampling ratio for MC method introduces high variance. In practice, it makes MC insufficient for off-policy prediction.

**B. In [[Temporal-Difference (TD) Policy Evaluation]]**

- The return $G_t^\mu$ is obtained from one-step lookahead and the rest is estimation. The importance-sampling formulation is given by
	$$G_t^{\pi/\mu} = \frac{\pi(A_t \mid S_t) * p_\mu(S_{t+1} \mid S_t, A_t)}{\mu(A_t \mid S_t) * p_\mu(S_{t+1} \mid S_t, A_t)} G_t^\mu = \frac{\pi(A_t \mid S_t) \mid S_t, A_t)}{\mu(A_t \mid S_t)\mid S_t, A_t)} G_t^\mu$$
	
> Observation: Importance-sampling in TD introduces much lower variance compared to MC method as thus, is more effective in practice.