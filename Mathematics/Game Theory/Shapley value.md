Given a [[Cooperative game]] defined by the characteristic function $v$, the Shapley value for the party $i$ measures the amount of payoff the party $i$ should be attributed. There are two ways to formalise its formula:
$$\varphi_i(v) = \frac{1}{n!} \sum_{C \subseteq N \setminus \{i\}}|C|!(n - |C| - 1)![v(C \cup \{i\}) - v(C)] \tag{1}$$
or equivalently,
$$\varphi_i(v) = \frac{1}{n} \sum_{C \subseteq N \setminus \{i\}}\frac{v(C \cup \{i\}) - v(C)}{n - 1 \choose |C|} \tag{2}$$
Intuitively, Shapley value is the marginal contribution of party $i$ to all other coalitions $C \subseteq N \setminus \{i\}$ on average. For an arbitrary coalition $C$, the contribution of party $i$ is $v(C \cup \{i\}) - v(C)$. Then, the number of coalitions is computed by:
- Choosing the order within the coalition, $|C|!$ ways. Next, choosing the order of other coalitions excluding the party $i$, $(n - |C| - 1)!$ ways. To get the average value, divide the multiplication by $n!$.
- Choosing the coalition having $|C|$ members from the list of parties $n - 1$ that excludes the party $i$ when the order doesn't matter. To get the average value, divide the multiplication by $n$.

<font color="red">Question: Why we have to average over all possible orders of users?</font>

### Synergy
The synergy function $w: 2^n \rightarrow \mathbb{R}$ is a function such that
$$v(S) = \sum_{R \subseteq S} w(R)$$

### Using Shapley values to attribute feature's contribution
Each feature corresponds to a player. A feature with unknown value, mapping to cooperative game, means that the player doesn't play the game.

In practice, from a specific prediction, we use Shapley value to determine the contributions of different features (with their specified values) to the prediction. Therefore, Shapley value shouldn't be intepreted as the difference in prediction if a feature is removed from our data.

### Comments
Shapley value is widely regarded as a principled notion of fairness, mostly due to its desired properties: symmetry and null player.

In explainable AI, Shapley values are used to distribute constribution to different features, given the accuracy of our predictions. That means, Shapley values can received any values (negative, positive, zero). "Shapley value is the average contribution of a feature value to the prediction, not the difference in prediction when we would remove the feature from the model".

It is impractical to calculate Shapley values in practice because its complexity increases with number of coalitions (which is permutations).