*Q: Best practice to use (first-order) optimizers?*
- SGD: differentiable objective functions (gradient can be computed for any given point in the input space)
- For stochastic objective functions ("almost surely nowhere differentiable" [1]), use:
	- AdaGrad: sparse-gradient
	- RMSProp: on-line and non-stationary settings
	- [[Adam]]:


[1] Kolmogorov-Chentsov Theorem and Differentiability of Random Fields on Manifolds