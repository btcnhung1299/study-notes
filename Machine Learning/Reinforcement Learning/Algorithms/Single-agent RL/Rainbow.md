# Annotations  
(21/07/2022, 15:19:07)

“- ever, it is unclear which of these extensions are complemen- tary and can be fruitfully combined.” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=5Q47C9TI))

“This paper examines six extensions to the DQN algorithm and empirically studies their combination.” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=N384XJS3))

“Double DQN (DDQN; van Hasselt, Guez, and Silver 2016) addresses an overestimation bias of Q-learning” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=JSEQDMTQ))

“Prioritized experience replay (Schaul et al. 2015) improves data efficiency” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=WI4PMX68))

“du- eling network architecture (Wang et al. 2016) helps to gen- eralize across actions” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=YFD2JELB))

“Learning from multi-step boot- strap targets (Sutton 1988; Sutton and Barto 1998), as used in A3C (Mnih et al. 2016), shifts the bias-variance trade- off” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=IHU87UFG))

“Distributional Q-learning (Bellemare, Dabney, and Munos 2017) learns a categorical distribution of discounted returns” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=PKS9DQWH))

“Noisy DQN (Fortunato et al. 2017) uses stochastic network layers” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=5W9SKVMM))

“Since they do so by addressing” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=5NFKNBUZ))

“Curves are smoothed  
with a moving average over 5 points” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=U4DNKRY9))

“radically different issues, and since they build on a shared framework, they could plausibly be combined” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=EJRWIZXS))

“In fact, their combination results in new state- of-the-art results on the benchmark suite of 57 Atari 2600 games from the Arcade Learning Environment (Bellemare et al. 2013), both in terms of data efficiency and of final perfor- mance.” ([Hessel et al., 2017, p. 1](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=1&annotation=CXQ9RMFG))

“The goal is to update θ such that this distribution closely matches the actual distribution of returns.” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=6ZYD7XBE))

“A distributional variant of Q-learning is then de- rived by first constructing a new support for the target dis- tribution, and then minimizing the Kullbeck-Leibler diver- gence between the distribution dt and the target distribution d0 t ≡ (Rt+1 + γt+1z, pθ(St+1, a∗t+1))” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=3M9V4R4D))

“Noisy Nets (Fortunato et al. 2017) propose a noisy linear layer that combines a deterministic and noisy stream” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=QUI7LA2V))

“allowing state-conditional exploration with a form of self-annealing” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=TPNNUDDR))

“we replace the 1-step distributional loss (3) with a multi-step variant.” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=SWEX8RRW))

“We combine the multi-step distributional loss with double Q-learning by using the greedy action in St+n selected ac- cording to the online network as the bootstrap action a∗t+n, and evaluating such action using the target network” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=4W6ZT96C))

“in our experiments all distributional Rainbow variants prioritize transitions by the KL loss, since this is what the algorithm is minimizing” ([Hessel et al., 2017, p. 3](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=3&annotation=ZWA3MJGW))

“Agents’ scores are normalized, per game, so that 0% cor- responds to a random agent and 100% to the average score of a human expert” ([Hessel et al., 2017, p. 4](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=4&annotation=64K6UEUB))

“Besides tracking the median performance as a function of environment steps, at the end of training we re-evaluate the best agent snapshot using two different testing regimes” ([Hessel et al., 2017, p. 4](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=4&annotation=4DJGGSUU))

“the  
difference between the two regimes indicates the extent to  
which the agent has over-fit to its own trajectories” ([Hessel et al., 2017, p. 4](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=4&annotation=TGW6LBB8))

“We have found that, with prioritized replay, it is possible to start learning sooner, after only 80K frames” ([Hessel et al., 2017, p. 4](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=4&annotation=CGRB9B8F))

“the KL loss of distributional DQN as priority, we have observed that performance is very robust to the choice of ω.” ([Hessel et al., 2017, p. 4](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=4&annotation=SUMZBWND))

“the first row we compare Rainbow to the baselines. On the second row we compare Rainbow to its ablations.” ([Hessel et al., 2017, p. 5](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=5&annotation=MZXQPKNW))

“In each ablation, we removed one component from the full Rainbow combination.” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=JNT9F5M3))

“Prioritized replay and multi-step learning were the two most crucial components of Rainbow, in that removing ei- ther component caused a large drop in median performance.” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=PZ92W3QV))

“Perhaps more surprisingly, the removal of multi- step learning also hurt final performance.” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=F9BJGJ5T))

“However, without distributions, the performance of the agent then started lagging behind” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=KTLEWKYR))

“There are many more algorithmic components that we  
were not able to include, which would be promising candi-  
dates for further experiments on integrated agents.” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=T78KRHZW))

“We have not considered purely policy- based RL algorithms such as trust-region policy optimisa” ([Hessel et al., 2017, p. 6](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=6&annotation=58MBMV9G))

“tion (Schulman et al. 2015), nor actor-critic methods (Mnih et al. 2016; O’Donoghue et al. 2016).” ([Hessel et al., 2017, p. 7](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=7&annotation=W3SEAAS8))

“To evaluate Rainbow fairly against the baselines, we have followed the common domain modifications of clipping re- wards, fixed action-repetition, and frame-stacking” ([Hessel et al., 2017, p. 7](zotero://select/library/items/4KE88FWF)) ([pdf](zotero://open-pdf/library/items/L8UUKQAU?page=7&annotation=XT83VYK9))