TD-error (short for Temporal-Difference) measures the difference between predicted values of [[value function]] and true ones encountered during interactions.
- In [[state-value function (utility)]]:
	$$\delta = R_{t+1} + \gamma V(S_{t+1}) - V(S_t)$$
- In [[value function]]:
	$$\delta = R_{t+1} + \gamma Q(S_{t+1}, A_{t+1}) - Q(S_t, A_t)$$