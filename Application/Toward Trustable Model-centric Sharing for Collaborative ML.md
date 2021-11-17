**Collaborative Machine Learning (CML)**
1. What is collaborative machine learning?
	- Train the model on aggregated data
	- Parties agree to provide their data on the basis of incentive rewards (e.g. financial rewards, or models as rewards [2])
2. What are the differences between collaborative machine learning and federated learning?
	- In CollabML, we have access to contributed data from contributors whereas in FL, we do not have access to local data
	- As a result, the model in collabML is trained in a centralized manner on the aggreated data while the model in FL is updated based on the aggreation of local updates
	- We can see FL as "gradient-based formulation of CollabML" [1] with
		- Models as rewards (?)
	- (Distributed) CML includes federated learning and split learning [3]
	<details>
	<summary>See the comparison [5]</summary>
		Clients in federated learning setting must fully-train local models, which is infeasible for resource-constrained devices and more severe with DNNs.
		In split learning, models are broken into multiple portions and trained sequentially by participating clients (no aggregation is needed).
	</details>

**Model-centric**:
	- Data-centric is traditional scheme, yet suffering from security and trust issues
	- Model-centric sharing: posit that models are "compact and self-contain with purpose-compiled knowledge from data"
	- In application, parties will share their heterogeneous *black-box* models instead of private data

---
**References**:
[1] Gradient Driven Rewards to Guarantee Fairness in Collaborative Machine Learning
[2] Collaborative Machine Learning with Incentive-Aware Model Rewards
[3] IEEE Call for Papers: Collaborative Machine Learning for Next-generation Intelligent Applications (https://www.comsoc.org/publications/journals/ieee-tnse/cfp/collaborative-machine-learning-next-generation-intelligent)
[4] SplitFed: When Federated Learning Meets Split Learning