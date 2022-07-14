Given a [[Cooperative game]] $v$, the Shapley value payoff of the party $i$ is defined as
$$\varphi_i(v) = \frac{1}{n!} \sum_{C \in N \setminus \{i\}}|C|!(n - |C| - 1)![v(C \cup \{i\}) - v(C)]$$\Intuitively, the formula concerns the party $i$'s **average contribution** $v(C \cup \{i\}) - v(C)$ over different ways (permutations) a coalition can be formed (there are $|C|!$ to form the coaltion and the others excluding our concerning party $i$ is $(n - |C| - 1)!$). 
 
Equivalently,
$$\varphi_i(v) = \frac{1}{n} \sum_{C \in N \setminus \{i\}}\frac{v(C \cup \{i\}) - v(C)}{n - 1 \choose |C|}$$
where $n - 1 \choose |C|$ is number of coaliations excluding $i$ of this size.


### Comments
Shapley value is widely regarded as a principled notion of fairness, mostly due to its desired properties: symmetry and null player.