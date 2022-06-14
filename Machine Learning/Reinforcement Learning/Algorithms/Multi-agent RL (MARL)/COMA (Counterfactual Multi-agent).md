
# Abstract
COMA employs [[Actor-Critic]] approach, in which critic is centralised and actor is decentralised. To attribute contributions to agents, formally known as credit assignment problem, COMA uses counterfactual baseline so that the decentralised actor can follow the policy gradient whose magnitude decided by its contribution to overall reward.

# Description
## Components
1. Centralised critic $Q(s, \mathbf{u})$ that conditions on central state $s$ and joint actions $\boldsymbol{u}$
2. Decentralised actor $\pi_a(u^a|\tau^a)$ that conditions on agent’s action-observation history

## Flow
1. Each decentralised actor $\pi_a(u^a|\tau^a)$ updates its parameters with respect to the policy gradient
	$g = f(A_a)$
	where $A_a$ is advantage function of agent $a$.
	Then, it chooses the next action $u_a^t$, which is sent to the centralised critic along with actions from other agents.
2. The centralised critic then updates its parameters and produce next advantage function $A_a$ for each agent.
![[Pasted image 20220606170400.png]]

## Novelty
1. To use actor-critic method, one naive approach is to let each agent actor follows the policy gradient based on the [[TD-error]] from the centralised critic. However, this approach fails to pay credit to different agents’ current actions, which is important in multi-agent settings, resulted in noisy signals during gradient updates. Therefore, the authors want to imply agent contributions from counterfactual baselines. The main idea is to let each agent learned from the so-called **shaped reward** $D_a = r(s, \mathbf{u}) - r(s, (\mathbf{u}^{-a}, c^a))$ where $c^a$ is the default action. Intuitively, we want to know if an agent instead acts randomly, how much reward we end up with.
2. Simulating the idea of default actions require significant resources. However, the authors mathematically show that the centralised critic can be used to implement the difference rewards that doesn’t exhause resources. Specifically, the advantage function is defined by
   $$A_t = ...$$
3. To further improve its practicibility for critic in case it is a DNN, the authors design critic so that it can output advantage function of all agents in one forward pass.

## Experimental settings


“to address the challenges of multi-agent credit as- signment, it uses a counterfactual baseline that marginalises out a single agent’s action, while keeping the other agents’ actions fixed” ([Foerster et al., 2017, p. 1](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=1&annotation=7KWKSLDB)) abstract point


“culating an aristocrat utility (Wolpert and Tumer 2002), but avoids the problem of a recursive interdependence between the policy and utility function because the expected contri- bution of the counterfactual baseline to the policy gradient is zero” ([Foerster et al., 2017, p. 2](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=2&annotation=2UG6LMX7))

“Three main ideas underly COMA: 1) centralisation of the critic, 2) use of a counterfactual base- line, and 3) use of a critic representation that allows efficient evaluation of the baseline” ([Foerster et al., 2017, p. 3](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=3&annotation=BWACLNID))

“A key insight underlying COMA is that a centralised critic can be used to implement difference rewards in a way that avoids these problems” ([Foerster et al., 2017, p. 4](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=4&annotation=X6F9BY8A))

“πa(u0a|τ a)Q(s,(u −a, u0a))” ([Foerster et al., 2017, p. 4](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=4&annotation=XATVBLWL))

“the counterfactual base- line’s expected contribution to the gradient, as with other policy gradient baselines, is zero” ([Foerster et al., 2017, p. 4](zotero://select/library/items/R5XUDVM2)) ([pdf](zotero://open-pdf/library/items/D5G44DQ7?page=4&annotation=HI6TF2CQ))
