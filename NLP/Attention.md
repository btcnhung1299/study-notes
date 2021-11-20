**Motivation**:
Fixed-sized context vectors (in encoder) are not effective to compress knowledge (for decoder to uncompress), especially when the source text is long (e.g., long input in machine translation)
-> Adaptively generate context vectors for each time step in output to soft-search for relevant part. That is, for each output token, we have an unique attention vector of input.

**Procedure**:
Let consider the encoder-decoder architecture:

$$p(y_t \mid y_1, \dots, y_{t-1}, \mathbf{x}) = g(c_t)$$
where $g$ is the decoder (that outputs the probability of the translation sequence) with input is the encoding vector specific to the current timestep $t$.

In the view of RNN, the encoding vector $c_t$ is a function of the previous context vector and the hidden states (from the encoder) $\mathbf{h}$. This function is regared as "attention", in which it computes the attentive coefficients to each hidden state in the input.
$$c_t = \sum_{i} \alpha_{ti}h_i$$
where $\alpha_{ti} = \frac{\exp (e_{ti})}{\sum_{j} \exp (e_{tj})}$ and $e_{ti} = a(c_{t-1}, h_i)$ with $a$ is a learnable model (suggested to be a FFN in [0])

*Note*: $h_i$ is claimed to be expressive for the token $i$ ("contains information about the whole input sequence with a strong focus on the parts surrounding the $i$-th word")

**References**:
[0] Neural Machine Translation by Jointly Learning to Align and Translate