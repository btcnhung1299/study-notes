**Approach**:
1. Compute gradient $g_t$
2. Compute two directions with [[momentum]], or "moment estimate" [1]
$m_t \leftarrow \beta_1 m_{t-1} + (1-\beta_1)g_t$
$v_t \leftarrow \beta_2 v_{t-1} + (1-\beta_2) g_t^2$
3. Correct bias for previous moment estimate
$\widehat{m}_t \leftarrow \frac{m_t}{1-\beta_1^t}$
$\widehat{v}_t \leftarrow \frac{v_t}{1-\beta_2^t}$
4. 

---
*Q: Why the second decay rate $\beta_2$ is often chosen to be larger than $\beta_1$* (best practice suggests $\beta_1=0.9, \beta_2=0.999$)

[1] Adam: A Method for Stochastic Optimization