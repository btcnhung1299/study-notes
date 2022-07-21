A **combination** concerns a selection of items from a set such that the order doesn't matter.
Concretely, choosing $k$ elements from a set of $n$ elements where the order doesn't matter resulting in $C(n, k)$ ways
$$C(n, k) = {n \choose k} = \frac{n!}{k!(n-k)!}$$
Also, these numbers are regarded as *binomial coefficients*, denoted by $n \choose k$.
The multinomial coefficients are ${n \choose {k_1, k_2, \dots, k_m}} = \frac{n!}{k_1!, k_2!, \dots, k_m!}$.  

A **permutation** concerns a selection of items from a set such that the order matters.
Concretely, choosing $k$ elements from a set of $n$ elements where the order matters resulting in $P(n, k)$ ways
$$P(n, k) = n! \cdot (n-1)! \cdots (n-k-1)! = \frac{n!}{(n-k)!}$$
### Relation between combinations and permutations
Intuitively, each combination of $k$ elements will have $k!$ permutations. Therefore, 
$$P_k^n = C_k^n \times k!$$
or equivalently,
$$\frac{n!}{(n-k)!} = \frac{n!}{k!(n-k)!} \times k!$$