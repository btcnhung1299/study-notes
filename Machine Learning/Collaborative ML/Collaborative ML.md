Collaborative ML is a paradigm that allows training on an aggregated data from many parties.

### Problem settings
1. Components:
	- $n$ (honest) parties: own the data $D_i \triangleq (\boldsymbol{X}_i, \boldsymbol{y}_i)$ for the i-th party (the parties are self-interested) 
	- 1 (trusted) central party: aggregate the data $D_C = \{D_i\}_{i \in C}$ 
2. Interactions:
	- Multiple parties team up as a coalition $C$. Multiple coalitions create a coalition structure $CS$. Two different coalition has no parties in common, i.e. $C \cap C' = \emptyset, \forall C, C' \in CS \text{ where } C \neq C'$. 
	- Each aggregated data $D_C$ of the coalition $C$ is tagged with a value, namely **value of the (aggregated) data** $v_C$ defined by the *characteristic function* $v_C: 2^N \rightarrow \mathbb{R}$
	- In return, each party $i$ will get **value of its received model reward** $r_i$
3. Objectives:
	- Design/**Optimise a reward scheme** that outputs $r_i$ for each participating party $i$
	- The scheme should satisfy certain incentives (e.g. fairness, stability)

### Challenges
1. Parties are reluctant to donate their data and lose their competitive edge unless we can design a good reward scheme. To ***design a good scheme***, we need to decide how to:
		1. Ensures faireness, stability, etc. in such scheme
		2. In what form the values of reward scheme should be (e.g. money, model, gradient, synthetic data - which is task- and model-agnostic)
2. To measure the data quality, we rely on the model quality that was trained by using that data. The model quality is evaluated via validation accuracy, which is subject to the validation dataset. As different parties might have different preferred test queries (e.g. hospital A wants to predict the diabetes of female while hospital B wants to predict for the young), it is hard to have a common validation test set (***data valuation***). On the other hand, the data value usually defined to reflect its contribution to model quality. In some cases, the party only wants to exploit others' contribution but unwilling to share their own data or intentially contribute low quality data. A design scheme ideally should penalise the party for that based on low data valuation.
3. ***Adapt different learning paradigm*** in a collaborative settings
	- Bayesian optimisation: [Sim et al., 2021] argues that a reward scheme in collaborative BO must have both efficiency (maximise the evaluated function values, or cumulative utilities) and fairness (reducing the differences between the cumulative utilities of all parties)

### Literature Review
| Citations | Addressed challenges | Description |
| --- | --- | --- |
| [Sim et al., 2020](zotero://select/library/items/F7HL4LGU) | 1.1 <br> 1.2 <br> 2 | Novel Shapley-based reward, robust to freely-adaptable problem; <br> Values of reward (model) are injected Gaussian noise with an optimised noise variance <br> Information gain data valuation: better data reduces model uncertainty |
| [Xu et al., 2021](zotero://select/library/items/7MQJGRTZ); [code](https://github.com/XinyiYS/Gradient-Driven-Rewards-to-Guarantee-Fairness-in-Collaborative-Machine-Learning) | 1.2 <br> 2 <br> 1.1 | Gradient reward based on FL <br> Data (i.e. gradient) validation based on cosine similarity, thus cosine gradient Shapley value <br> Gradients are applied with the sparsifying gradient trick to ensure fairness |
| [Tay et al., 2021](zotero://select/library/items/CCJXI6AA); [code](https://github.com/XinyiYS/CML-RewardDistribution) | 1.2 <br> 2 | Synthetic data as rewards (model- and task-agnostic) <br> Data valuation based on maximum mean discrepancy: its closeness to the aggregated data's distribution |
| [Xu et al., 2021](zotero://select/library/items/ZT67V8AA); [code](https://github.com/ZhaoxuanWu/VolumeBased-DataValuation) | 2 | Validation based on data diversity: measured by volume of data matrix, modified as robust volume to avoid data replication. The robust volume is used as a charactistic function in Shapley value. |
| [Sim et al., 2021](zotero://select/library/items/3C5XUXFX) | 3 <br> 1.1 | Collaborative Bayesian optimisation; Adapted constraints: fair regret based on generalised Gini social-evaluation function 

### Questions
1. We have two different values: data valuation and reward. How can we decide reward based on data valuation (keeping in mind that the monotonicity should be kept).