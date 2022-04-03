**Original paper**: [Simple Statistical Gradient-Following Algorithms for Connectionist Reinforcement Learning](https://link.springer.com/article/10.1007/BF00992696)

REINFORCE, or Monte-Carlo [[Policy Gradient (Model-Free Policy-based RL)]], employs [[Policy Gradient (Model-Free Policy-based RL)]] to find the optimal paramaters of the parametric stochastic policy that maximize the [[action-value function (Q-function)]].

REINFORCE utilizes Monte-Carlo method to obtain unbiased sample of action values $Q_\pi(s,a)$ based on the fact that [[action-value function (Q-function)]] is the expected [[return (cumulative reward)]], denoted as $G_t$. The SGD update becomes
$$\theta \leftarrow \theta + \alpha \nabla \log \tilde{\pi}(a \mid s, \theta) G_t$$
where $G_t$ is the tracking avaraged return.

***Pseudocode***:
![400](REINFORCE.PNG)
where $v_t$ is alternative notation for $G_t$.