*Approach*: Replace basic layers in encoder-decoder to [[attention]] (instead of recurrence or convolution)

**Model architecture**:
![300](./resources/AttentionIsAllYouNeed-Figure1.png)

*Note*:
- Signals are combined from the encoder **and** masked attention values from the output. Intuitvely, it allows us to make prediction based on information from the input and the output up to this point.
- [[Residual]] connections are applied around each layer before normalized

**Novel blocks**:
1. Multi-Head Attention:
- Attention parameters (i.e., $\mathbf{K}, \mathbf{V}, \mathbf{Q}$) are linearly projected by $\mathbf{W}^K_i, \mathbf{W}^V_i, \mathbf{W}^Q_i$ in $i$-th head
- Output vectors from multiple heads are concatenated and linearly projected by $\mathbf{W}_O$ to create final output

	$$
	\begin{align}
	\mathrm{MultiHead}(\mathbf{K}, \mathbf{V}, \mathbf{Q}) &= \mathrm{concat}(\mathrm{head}_1, \cdots, \mathrm{head}_h) \mathbf{W}_O \\
	\mathrm{where} \quad \mathrm{head}_i &= \textrm{attn}(\mathbf{K}\mathbf{W}^K_i, \mathbf{V}\mathbf{W}^V_i, \mathbf{Q}\mathbf{W}^Q_i)
	\end{align}
	$$

	*Note*:
	- $\mathrm{attn}$ denotes a particular attention variant, namely Scaled (by $\sqrt{d_k}$) Dot-Product (instead of additive) Attention
	$$
	\begin{align}
	\textrm{attn}(\mathbf{K}, \mathbf{V}, \mathbf{Q}) &= \frac{\mathbf{Q}\mathbf{K}^{\intercal}}{\sqrt{d_k}} \mathbf{V} \\
	&(n \times d_k) (d_k \times n) (n \times d_v)
	\end{align}
	$$
	- The size of $d_k, d_v$ is scaled by the number of heads => the total computation cose of multi-head attention layer is the same as single-head one

2. Positional Encoding
- 