A Nash equilibrium is a point (i.e. joint action vectors of $n$ agents in the game) in which each single-agent action is best response to $n-1$ other players. Intuitively, point that is not Nash equilibrium will have unsettling property: that is, there exists an agent whose its action can be taken differently in order to improve the current profit of the joint.

Concretely, given $r(a_i)$ be reward for agent $i$ taking action $a_i$. Then, it is said to satisfy the Nash equilibrium if
$$r(a_1^*, \dots, a_n^*) \geq r(a_1^*, \dots, a_{i-1}^*, a_i, a_{i+1}^*, \dots, a_n^*), \forall i \in [1, n]$$
Intuitively, suppose all agent strategies are stated publicly, Nash equilibrium will result in no agent making a change in their strategies. Nash equilibrium gives rise to the creation of [[Prisoner's Dilemma]].

Nash equilibrium defines over a **non-cooperative game**.