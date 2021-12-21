**Description**: a sequence of agent interacting with the environment, described by series of tuple (state, action, reward), until terminal state is reached.

**Formulation**:
$$\tau = (s_0, a_0, s_1, a_1, r_1, \dots, s_T)$$
where $T$ is trajectory/episode size.

*Note*: There is neither $r_0$, or reward at the beginning nor   $a_T, r_T$ - action and reward at the terminal state.