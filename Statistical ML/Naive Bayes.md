**Purpose**: a classifier

Let $\mathbf{x} = \{x_1, \dots, x_k\}$ is a feature vector for a sample.
*Assumption*: All features are independent. That is, $x_1 \perp \dots \perp x_k$.

**Formulation**: the probability of a sample represented by $x$ belongs to class $\mathcal{C}_i$ is the conditional probability:
$$\begin{align}
&P(\mathcal{C}_i \mid \mathbf{x}) \\ 
&= P(\mathcal{C}_i \mid x_1, \dots, x_k) \tag{1}
\end{align}$$

Observations: It is hard to trace the joint probability $(x_1, \dots, x_k)$ because we need to keep track of joint probability of all combinations, or a probabability table, which is infeasible.

**Solution**: Apply [[Bayes' theorem]], that is
$$P(\mathcal{C}_i \mid \mathbf{x}) 
= \frac{P(\mathbf{x} \mid \mathcal{C}_i) * P(\mathcal{C}_i)}{P(\mathbf{x})}$$
where $P(\mathbf{x}) = P(x_1) * \dots * P(x_k) = \text{constant}$ because of the independence assumption and can safely be removed (which, as a result, the final $P(\mathcal{C}_i \mid \mathbf{x})$ we get is not the "true" probability).

$$P(\mathcal{C}_i \mid \mathbf{x})
\propto P(\mathbf{x} \mid \mathcal{C}_i) * P(\mathcal{C}_i) = P(\mathbf{x}, \mathcal{C}_i)$$

Unpack the joint $P(\mathbf{x}, \mathcal{C}_i)$ by conditional probabilities (see [[Marginal, Joint, and Conditional Probabilities]]), we got:
$$\begin{align}
P(\mathbf{x}, \mathcal{C}_i)
&= P(x_1 \mid x_2, \dots, x_k, \mathcal{C}_i) * \dots * P(x_k \mid \mathcal{C}_i) * P(\mathcal{C}_i) \\
&\stackrel{x_1 \perp \dots \perp x_k}{=} P(x_1 \mid \mathcal{C}_i) * \dots * P(x_k \mid \mathcal{C}_i) * P(\mathcal{C}_i) \\
&= P(\mathcal{C}_i) \prod_{t=1}^{k} P(x_t \mid \mathcal{C}_i)
\end{align}$$
or
$$P(\mathcal{C}_i \mid \mathbf{x})
\propto P(\mathcal{C}_i) \prod_{t=1}^{k} P(x_t \mid \mathcal{C}_i)$$

**Extension**:
- Gaussian Naive Bayes:
$$P(x_t = v \mid \mathcal{C}_i) = \frac{1}{\sqrt{2 \pi \sigma^2_i}} \exp(-\frac{(v - \mu_i)^2}{2 \sigma^2_i})$$
- Multinomial Naive Bayes:
$$P(x_t \mid \mathcal{C}_i) = \frac{}{}$$