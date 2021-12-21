 Let $p(\mathbf{x} \mid \theta) = p_{\theta}(\mathbf{x})$ describe the **joint probability** of observations $\mathbf{x}$ when we use the implied statistical model with parameter $\theta$.

Example: Suppose you asked 100 people and observed that 55 of them said yes. If you believe that underlying probability distribution is the binomial distribution with parameters $\theta$, then you'll get the probability of saying yes as
$$p(55 \mid \theta) = p_{\theta}(55) = {100 \choose 55} \theta^{55} (1-\theta)^{100-55}$$

*Observations*:
- Typically, we want to find $\theta$ that best describes your data. That is, when you plugged it into the above equation, you get the maximum probability. In this case, $p_{\theta}(\mathbf{x})$ is a p.d.f (see [[PDF and CDF]]) of the parameters $\theta$.
- Hence, the function you want to optimise has $\mathbf{x}$ as a condition, referred as **likelihood function** $\mathcal{L}(\theta \mid \mathcal{x})$. Finding optimal $\theta$ is thus called [[Maximum Likelihood Estimate (MLE)]].