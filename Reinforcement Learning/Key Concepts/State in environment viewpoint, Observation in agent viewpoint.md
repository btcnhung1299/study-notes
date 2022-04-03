## State
State in reinforcement learning refers to the state of the environment the agent is lived in. The state is always complete on its own.
An environment state can be changed due to the actions from agents or by it own.

## Observation
Observation in reinforcement learning refers to the observation of the environment state that an agent sees, which can be *fully-observable* or *partially-observable* (mathematically described in [[Partial-Observable MDP (POMDP)]]).

---

# FAQ
1. **Q**: Are state and observation interchangeable?
	**A**: No. State is all information about the world, whereas some information can be omitted in an observation, or a partial description. Nevertheless, state is widely (and misleadingly) used most of the time.