# Annotations  
(23/06/2022, 21:52:59)

“Whereas standard policy gra- dient methods perform one gradient update per data sample, we propose a novel objective function that enables multiple epochs of minibatch updates” ([Schulman et al., 2017, p. 1](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=1&annotation=AS823J88))

“The new methods, which we call proximal policy optimization (PPO), have some of the benefits of trust region policy optimiza- tion (TRPO)” ([Schulman et al., 2017, p. 1](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=1&annotation=2TJ3UEKX))

“This paper seeks to improve the current state of affairs by introducing an algorithm that attains the data efficiency and reliable performance of TRPO, while using only first-order optimization” ([Schulman et al., 2017, p. 1](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=1&annotation=PRABT7FJ))

“We propose a novel objective with clipped probability ratios, which forms a pessimistic estimate (i.e., lower bound) of the performance of the policy” ([Schulman et al., 2017, p. 1](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=1&annotation=E4EZDNRG))

“While it is appealing to perform multiple steps of optimization on this loss LP G using the same  
trajectory, doing so is not well-justified, and empirically it often leads to destructively large policy  
updates (see Section 6.1; results are not shown but were similar or worse than the “no clipping or  
penalty” setting)” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=4GLAWY8S))

“TRPO \[Sch+15b\], an objective function (the “surrogate” objective) is maximized subject to a constraint on the size of the policy update” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=XI2WY52T))

“The theory justifying TRPO actually suggests using a penalty instead of a constraint, i.e., solving the unconstrained optimization problem” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=WRSGFCU8))

“maximize θ Eˆ t πθ(at | st) πθold(at | st)Aˆ t − β KL\[πθold(· | st), πθ(· | st)\]” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=P668FSRR))

“for some coefficient β” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=HRNLGAF6))

“TRPO uses a hard constraint rather than a penalty because it is hard  
to choose a single value of β that performs well across different problems” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=HWUKHQTM))

“Hence, to achieve our goal  
of a first-order algorithm that emulates the monotonic improvement of TRPO, experiments show  
that it is not sufficient to simply choose a fixed penalty coefficient β” ([Schulman et al., 2017, p. 2](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=2&annotation=ET88NT6F))

“Without a constraint, maximization of LCP I would lead to an excessively large policy update” ([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=6HFL6DH6))

“LCLIP (θ) = Eˆ thmin(rt(θ)Aˆ t, clip(rt(θ), 1 − , 1 + )Aˆ t)i” ([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=RHFNCZ2B))

\[image\] ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=76QMF7I5))  
([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS))

“removes the incentive for moving rt outside of the interval \[1 − , 1 + \]” ([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=3PRWHY3K))

“take the minimum of the clipped and unclipped objective, so the final objective is a lower bound” ([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=PUB6SHST))

“With this  
scheme, we only ignore the change in probability ratio when it would make the objective improve,  
and we include it when it makes the objective worse” ([Schulman et al., 2017, p. 3](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=3&annotation=RZRY45G8))

“Another approach, which can be used as an alternative to the clipped surrogate objective, or in addition to it, is to use a penalty on KL divergence, and to adapt the penalty coefficient so that we achieve some target value of the KL divergence dtarg each policy update” ([Schulman et al., 2017, p. 4](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=4&annotation=HPWPUTUX))

“In our experiments, we found that the KL penalty performed worse than the clipped surrogate objective, however, we’ve included it here because it’s an important baseline” ([Schulman et al., 2017, p. 4](zotero://select/library/items/DKGZ4GGS)) ([pdf](zotero://open-pdf/library/items/UCF4NL4Q?page=4&annotation=CBAFNKZW))