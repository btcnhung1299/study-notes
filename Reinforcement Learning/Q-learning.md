**Description**: In which a [[Temporal-Difference (TD)]] agent learn [[Q-function]], not [[utility]].

**Formulation**:
$$Q(s,a) \leftarrow Q(s,a) + \alpha \left[ R(s) + \gamma \max_{a^{\prime}} Q(s^{\prime}, a^{\prime}) - Q(s,a) \right]$$
where $Q$ is a [[Q-function]] and $\alpha$ is learning rate.

*Observations*: No need to learn a transition model $P(s^{\prime} \mid s, a)$ -> Q-learning is a **model-free method**.