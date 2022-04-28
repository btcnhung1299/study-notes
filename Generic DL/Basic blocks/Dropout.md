**Approach**:
Drop several units as well as its incoming and outcoming connections

**Goal**:
- Prevent overfitting: learn noise relationship (frequently in limited data)
- A realization of model combination (which is claimed to typically improve the performance)
<details>
	Using dropout on a neural network with $n$ units, we are sampling on $2^n$ different *thinned* networks
</details>

*Note on implementation*:
At test time, it is expensive to average predictions from exponential ($2^n$) different thinned networks.
=> Trick: let the output of a hidden unit at test time equals to its *expected output* at training time. Concretely, the hidden unit with dropout rate $p$ will have its weight $w$ scaled as $p*w$ at test time.

---
*Q: Is there any difference between dropout probability for inputs and hidden units*
A:
- Dropout rate for hidden units can simply be set at 0.5
- Dropout rate for inputs is usually closer to 1 than 0.5

*Q: How should dropout be used in combination with other hyper-parameters*:
A: As suggested in [1], dropout should be used along with
- Max-norm regularization: bound the weights within a ball of radius $c$, i.e. $||w||_2 \leq c$
- High momentum: within a constrained space, dropout allows using high momentum to exhausively explore the space without weights being blown up
- Large decaying lr: take shorter steps after each iteration and ultimately rest in the minimum



**References**:
[1] Dropout: A Simple Way to Prevent Neural Networks from Overfitting