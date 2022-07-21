Data valuation seeks to determine a value (or a value vector) for data points.

## Problem settings
For a dataset $D = \{z_i\}_{i=1}^N$, an utility function $U(S)$ defines the values of data aggregation $S$. We want to find a function $s$ that will assign value to a datum $z_i$ as $s(U, z_i)$.

## Challenges
0. How to measure your data? (What is your data worth?)
1. Data valuation is associated with multiple factors: learning algorithm (certain data points can be important for LR model but trivial for DNN); ML problem (supervised/unsupervised/etc.); performance metrics (on a common validation dataset). In the context of collabML/distributed ML, these associations cause troubles because data/updates are pooled from different sources.
2. As number of data points (datum) can be extremely large, data valuation must be efficient enough.
3. When data points got replicated, data valuation must be flexible enough to not give the same amount of values for the duplication.
4. In practice, data values among a group of people must satisfy fairness, rationality, and decentralisability.
5. In some settings (e.g. FL), data valuation must take into account the participation order of a data point. As the model tends to shrink its updates after training for a while, data values of important data points but only consider at the end of the training tends to receive lower values than their actual contribution.

## Literature review
| Link | Addressed Challenges | Description |
| --- | --- | --- |
| Leave-one-out (LOO) | 0 | Contribution of a datum is the performance difference when include and exclude that datum |
| [Ghorbani and Zou, 2019](zotero://select/library/items/64XVCBNB) | 2 <br> 4 | Data Shapley approximates Shapley Value using Monte Carlo simulation <br> The Shapley Value achieves different desirable real-world properties <br> The valuation targets at supervised ML |
| [Xu et al., 2021](zotero://select/library/items/ZT67V8AA) | 1 <br> 0, 3 | Valuate data based on intrinsic nature: data volume <br> Propose robust volume to cope with replication |
| [Wang et al., 2020](zotero://select/library/items/G3ZUT56V)| 5 | Federated Shapley value |
| [Yoon et al., 2019](zotero://select/library/items/TTSHHH6R) | 0 | Learn data distribution (likelihood) by estimating data value as selection probabilities and use RL (REINFORCE) to backprop the training signal |
| [Jia et al., 2020](zotero://select/library/items/TRPK53DQ) | 2 | 

On the other hand, data valuation can be seen as assigning appropriate weight to each datatum.


## Application
- Detecting corrupted samples
- Select important samples for adaptation
- 