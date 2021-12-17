*Approach*: Replace basic layers in encoder-decoder to (multi-headed) self-[[attention]] (instead of recurrence or convolution)

**Model architecture**:
![300](./resources/AttentionIsAllYouNeed-Figure1.png)

*Observations*:
- In decoding, we will combine hidden state from the encoder **and** masked attention values from the output. Intuitvely, it allows us to make prediction based on the latent input representation as well as our preditions for the previous tokens.
- [[Residual]] connections are applied around each layer before normalized.

**Novel blocks**:
1. Multi-Head Attention:
- Attention parameters (i.e., $\mathbf{K} \in \mathbb{R}^{n \times d_k}, \mathbf{V} \in \mathbb{R}^{n \times d_v}, \mathbf{Q}^{n \times d_k}$) are linearly projected by $\mathbf{W}^K_i, \mathbf{W}^V_i, \mathbf{W}^Q_i$ in the $i$-th head
- Output vectors from multiple heads are concatenated and linearly projected by $\mathbf{W}_O$ to create final output

	$$
	\begin{align}
	\text{MultiHead}(\mathbf{K}, \mathbf{V}, \mathbf{Q}) &= \text{concat}(\text{head}_1, \cdots, \text{head}_h) \mathbf{W}_O \\
	\text{where} \quad \text{head}_i &= \text{SDPAttention}(\mathbf{K}\mathbf{W}^K_i, \mathbf{V}\mathbf{W}^V_i, \mathbf{Q}\mathbf{W}^Q_i)
	\end{align}
	$$

	*Note*:
	- Scaled (by $\sqrt{d_k}$) Dot-Product (instead of additive) Attention:
	$$\text{SDPAttention}(\mathbf{K}, \mathbf{V}, \mathbf{Q}) = \frac{\mathbf{Q}\mathbf{K}^{\intercal}}{\sqrt{d_k}} \mathbf{V}$$
	- The size of $d_k, d_v$ is scaled by the number of heads => the total computation cose of multi-head attention layer is the same as single-head one

2. Positional Encoding
- Where: Input = embedding + positional encoding (taking sum)
- Which: sinusoidal (sine wave) functions
$$
\text{PE}(pos, i) =
\begin{cases}
\sin \left(\frac{pos}{10000^{2k/d}} \right), & \text{if } i=2k \\
\cos \left(\frac{pos}{10000^{2k/d}} \right), & \text{if } i=2k+1
\end{cases}
$$
where $\text{PE}(pos, i)$ is the value at position $pos$ in $i$-th dimension of the encoding. The angular frequency $\omega = \frac{1}{10000^{2k/d}}$ denotes the function's rate of change.


**References**:
[0] Attention Is All You Need
[1] https://kazemnejad.com/blog/transformer_architecture_positional_encoding/