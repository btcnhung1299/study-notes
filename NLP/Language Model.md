**Goal**: Predict the probability of a sequence of words $P(w_1, w_2, ..., w_n)$

**Equivalent formulation**: with chain-rule (order-restricted) (see [[Marginal, Joint, and Conditional Probabilities]])
	
$$\begin{align}
P(w_1, ..., w_n) = \prod_{i=1}^n P(w_i \mid w_1, ..., w_{i-1}) \tag{1}
\end{align}$$
	
1. Statistical LM: directly computes [1] with counting, e.g., N-gram LM.
	- *Observation*: $P(w_1, ..., w_n)$ is easy to shrunk to 0 due to the **sparsity** of the modeled sequence in the corpus (e.g., $P(\text{week}|\text{I,played,football,last}) \approx 0$)
	- *Extension*: inspired by [[Markov assumption]], 

**N-Gram Language Model**

2. 


- Improved method: make [[Markov assumption]] to model the probability including the next word based on the current word *or sequence of words*
	$$P(w_1, ..., w_m) = \prod_{i}^m P(w_i \mid w_{i-1})$$

1. **N-gram Language Model** (different order of Markov model):
	$$P(w_1, ..., w_n) = \prod_{i}^n P(w_i \mid w_{i-1}, ..., w_{i-n})$$
	where $n << m$
	
2. **P(w)**: smoothing techniques
- [[Maximum Likelihood Estimate]]: $P(w_i) = \frac{\text{count}(w_i)}{N}$ where $N$ is corpus size
- Laplacian/Add-one: $P(w_i) = \frac{\text{count}(w_i) + 1}{N + V}$ where $V$ is vocabulary size

3. (Linear) **Interpolation**/Mixture: weight contribution of each $k$-gram model ($k \leq n$) => new another probability distribution. E.g., combine prediction of unigram, bigram, and trigram for a third-order LM.
	$$P(w_i|w_{i-1} w_{i-2}) = \lambda_1 P(w_i) + \lambda_2 P(w_i|w_{i-1}) + \lambda_3 P(w_i|w_{i-1} w_{i-2})$$

4. Back-off: recursively return to the lower order LM if the current probability is 0.
___
*Q: The unit of language model for different languages (English, Chinese, Japanese, Vietnamese, etc)?*
A: Based on the characteristics of the target language, we can use language model on words (English, Vietnamse) or characters (Chinese, Japanese)