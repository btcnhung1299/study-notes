Collaborative ML is a paradigm that allows training on an aggregated data from many parties.

### Problem settings
1. Components:
	- $n$ (honest) parties: own the data $D_i \triangleq (\boldsymbol{X}_i, \boldsymbol{y}_i)$ for the i-th party 
	- 1 (trusted) central party: aggregate the data $D_C = \{D_i\}_{i \in C}$ 
2. Interactions:
	- Multiple parties team up as a coalition $C$. Multiple coalitions create a coalition structure $CS$. Two different coalition has no parties in common, i.e. $C \cap C' = \emptyset, \forall C, C' \in CS \text{ where } C \neq C'$. 
	- Each aggregated data $D_C$ of the coalition $C$ is tagged with a value, namely **value of the (aggregated) data** $v_C$ 
	- In return, each party $i$ will get **value of its received model reward** $r_i$
3. Objectives:
	- Design a scheme that outputs $r_i$ for each participating party $i$
	- The scheme should satisfy certain incentives (e.g. fairness, stability)

### Challenges
1. Parties are reluctant to donate their data and lose their competitive edge unless we can design a good reward scheme. To design a good scheme, we need to decide how to:
	1. Value a party's data and its contribution to model quality
	2. Design a reward scheme that incentivise a collaboration
	3. In what form the values of reward scheme should be (e.g. money, model, synthetic data)
2. To measure the data quality, we rely on the model quality that was trained by using that data. The model quality is evaluated via validation accuracy, which is subject to the validation dataset. As different parties might have different preferred test queries (e.g. hospital A wants to predict the diabetes of female while hospital B wants to predict for the young), it is *hard to have a common validation test set*.

### Literature Review
- [Ghonorbani & Zou, 2019, Jia et al., 2019] fairly partitions $v_C$ into individual $r_i$ using results from CGT
- [Xu 2021] adopts federated learning paradigm and propose cosine gradient Shapley value to evaluate the data without testing on validation dataset
- 
- 

**Readings**:
1. Collaborative ML with Incentive-Aware Model Rewards
2. Gradient Driven Rewards to Guarantee Fairness in Collaborative ML
3. 

Constraints:
- Each party requires a cost to give away its data.
- The value of aggregated data typically reflects the data quality, e.g. whether it can be used to train a higehr-quality ML model
- 


