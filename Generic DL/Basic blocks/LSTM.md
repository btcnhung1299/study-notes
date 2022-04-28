**Idea**:
- Hidden vector: relies on output transformation and context vector.
- Context vector: relies on input transformation and some pieces of previous context.

**Formulation**:
1. Hidden vector $\mathbf{h}_t = \mathbf{o}_t \odot \tanh(\mathbf{c}_t)$
2. Context vector $\mathbf{c}_t = \mathbf{f} \odot \mathbf{c}_{t-1} + \mathbf{i} \odot \mathbf{g}$

In which $\mathbf{i}, \mathbf{o}, \mathbf{f}, \mathbf{g}$ is obtain from current input $\mathbf{x}_t$ and previous hidden state $\mathbf{h}_{t-1}$:
$$
\begin{align}
\mathbf{i} &= \sigma(\mathbf{h}_{t-1} \mathbf{U}_i + \mathbf{x}_t \mathbf{W}_i) \\
\mathbf{o} &= \sigma(\mathbf{h}_{t-1} \mathbf{U}_o + \mathbf{x}_t \mathbf{W}_o) \\
\mathbf{f} &= \sigma(\mathbf{h}_{t-1} \mathbf{U}_f + \mathbf{x}_t \mathbf{W}_f) \\
\mathbf{g} &= \sigma(\mathbf{h}_{t-1} \mathbf{U}_g + \mathbf{x}_t \mathbf{W}_g)
\end{align}$$


*Observation*:
- The XOR operation $\odot$ will omit similar elements, hence it acts as forgetting or attention mechanism
	- $\mathbf{f} \odot \mathbf{c}_{t-1}$: omit mismatch in context vector $\mathbf{c}$ with respect to the "forgetting vector" $\mathbf{f}$
	- $\mathbf{i} \odot \mathbf{g}$: omit mismatch in input vector $\mathbf{i}$ with respect to $\mathbf{g}$
