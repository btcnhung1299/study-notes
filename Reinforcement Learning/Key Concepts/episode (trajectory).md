Episode or trajectory, denoted as $\tau$, is a sequence of agent interacting with the environment, described by series of tuple (state, action, reward), until terminal state is reached.

$$\tau = (s_0, a_0, s_1, a_1, r_1, \dots, s_T)$$
where $T$ is trajectory/episode size.

**Note**: There is neither inital reward $r_0$ nor terminal reward-action $a_T, r_T$.