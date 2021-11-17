**Basic idea**: Find the common initializer (meta parameters) for a set of tasks such that it can easily adapt on these tasks by performing a few gradient steps.

**Concrete formulation**:
Let $\theta$ is the target initializer.
$m$ is the number of gradient steps for adaptation.

Let $g$ is the gradient w.r.t to task $t$

$$g_t^{(1)}(\theta) = \theta - \eta\nabla_{\theta}\mathcal{L}_t$$

Then the gradient after $m$ steps is recursively computed as
$$g_t^{(m)}(\theta) = g_t^{(1)}(g_t^{(m-1)}(\theta)) \text{ where } m \geq 2$$

The loss after adaptation for the task $t$ is
$$\mathcal{L}_t[y_t, g_t^{(m)}(\theta)]$$

We want the meta parameter is the one the common initializer that tasks can be adapted at well as possible.

$$\arg \min_\theta \sum_{t \in \mathcal{T}} \mathcal{L}_t[y_t, g_t^{(m)}(\theta)]$$

In the case when $m = 1$, we have the following objective function

$$\arg \min_{\theta} \sum_{t \in \mathcal{T}} \mathcal{L}_t[y_t, \theta - \eta \nabla_{\theta} \mathcal{L}_t]$$

$$\theta' - \eta[ \theta - \eta \nabla_{\theta} \mathcal{L}_t]$$

**First-order approximation**:

Taylor series approximation: $f(x) = f(a) + \frac{1}{1!}f'(a)(x-a) + \frac{1}{2!}f''(a)(x-a)^2 + \cdots$
