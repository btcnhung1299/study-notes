**Formulation**:
$$Q(s,a) \leftarrow Q(s,a) + \alpha \left[ R(s) + \gamma \max_{a^{\prime}} Q(s^{\prime}, a^{\prime}) - Q(s,a) \right]$$

*Observations*: Using Q-learning, we don't have to learn a transition model $P(s^{\prime} \mid s, a)$ -> Q-learning is a **model-free method**.

**Application**:
- Typically use with [[Temporal-difference (TD)]] because [[Adaptive Dynamic Programming (ADP)]] requires tracking statistics of $P(s^{\prime} \mid s, a)$