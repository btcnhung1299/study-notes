In entropy regularisation, entropy refers to the predictability of an action an agent might take, or intuitively, the certainty that our policy will give highest reward.

In practice, when achieving good reward by taking an action $a$, an agent can stick with $a$ without exploring other better options. In other words, taking an action $a$ has low entropy. Therefore, entropy regularisation can help exploration by optimising:
$$\pi^* = \arg \max_{\pi} \mathbb{E}_{s \sim p^\pi} [R + H(\pi)]$$
where $H$ is entropy of the policy distribution $\pi$.