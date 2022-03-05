Bayes' theorem combines the sum rule and chain rule between [[Marginal, Joint, and Conditional Probabilities]] by:
$$\begin{align}
P(A, B) &= P(B, A) \\
\Leftrightarrow P(A \mid B)*P(B) &= P(B \mid A) * P(A) \end{align}$$
or more popular:
$$P(A \mid B) 
= \frac{P(B \mid A) * P(A)}{P(B)} 
= \frac{P(B \mid A) * P(A)}{\sum_A P(B, A)}$$
where $P(A)$ is referred to as **prior probability** of $A$ (probability before seeing evidence) and $P(A \mid B)$ as **posterior probability** of $A$ given $B$ (probability after seeing evidence).