**Method**: Keep a running average of total reward at each state in different trials. By the law of large number, the more observations we get for this value at state $s$, the closer it gets to the true expectation of total reward, or [[Value Function (Utility)]] at that state.

**Formulation**: Direct utility estimation can be viewed as a supervised problem where input is the state and [[Value Function (Utility)]] as output.

**Disadvantage**:
- Violate the nature of states, or [[Bellman equation]]: states are not independent from each other -> slow converge