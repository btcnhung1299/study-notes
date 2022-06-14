# Annotations  
(07/06/2022, 12:09:06)

“existing methods have been focusing on learning fully decentralized value functions, which are not efficient for tasks requiring com- munication” ([Wang et al., 2020, p. 1](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=1&annotation=6EEJ8WK5))

“this paper presents a novel framework for learning nearly decomposable Q-functions (NDQ) via communication mini- mization, with which agents act on their own most of the time but occasionally send messages to other agents in order for effective coordination” ([Wang et al., 2020, p. 1](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=1&annotation=WXIMUM2B))

“introducing two information-theoretic regularizers. These regularizers are maxi- mizing mutual information between agents’ action selection and communication messages while minimizing the entropy of messages between agents” ([Wang et al., 2020, p. 1](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=1&annotation=C5T76MBZ))

“many multi-agent tasks in the real world are not fully decomposable – agents sometimes require information from other agents in order to effectively coordinate their behaviors” ([Wang et al., 2020, p. 1](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=1&annotation=XMNH896Y))

“ensure communication to be both expressive (i.e., effectively reducing the uncertainty of agents’ action- value functions) and succinct (i.e., only sending useful and necessary information)” ([Wang et al., 2020, p. 2](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=2&annotation=F8QQUCQ9))

“m(-i)j is used to denote the messages sent to j from agents other than i” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=GSTQUEWJ))

“To learn such a communicating strategy, we draw inspiration from variational inference for its proven ability in learning structure from data and endow a stochastic latent message space, which we also refer to as ”message embedding”.” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=97LCW7TH))

“Agent j will receive an input message min j” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=N86IEFFD))

“it conditions the local action-value function Qj (τj , aj , min j ). All the individual Q values are then fed into a mixing network such as that used by QMIX (Rashid et al., 2018).” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=94RZ6822))

“all the components (the individual action- value functions, the message encoder, and the mixing network) are trained in an end-to-end manner by minimizing the TD loss” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=ACCVYEF5))

“L(θ) = LTD(θ) + λLc(θc)” ([Wang et al., 2020, p. 3](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=3&annotation=DLYMQI6G))

“To make mes- sage expressive, we maximize the mutual information between message and agent’s action selection” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=5GLF2WIS))

“Iθc (Aj ; Mij |Tj , M(-i)j ) where Aj is agent j’s action selection, Tj is the random variable of the local action-observation history of agent j, Mij and M(-i)j are random vari- ables of mij and m(-i)j” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=JSSER6SD))

“However, if this is the only objective, the encoder can easily learn to cheat by giving messages under different histories representations in different regions in the latent space” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=YLXZDHR4))

“natural constraint to avoid such representations is to minimize the entropy of the messages” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=ZR8VXSWF))

“computation” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=FPKGBMVB))

“involving mutual information is intractable” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=RC9QRSPF))

“By introducing a variational approximator, a popular technique from variational toolkit (Alemi et al., 2017), we can derive a lower bound for the mutual information term” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=T556N4XL))

“minimize the term Hθc (Mij ). Directly minimizing this can cause the variances of the Gaussian distributions to collapse to 0” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=2F6GTESH))

“To deal with this numeric issue, we use the unit covariance matrix and try to minimize H(Mij ) − H(Mij |Ti) instead” ([Wang et al., 2020, p. 4](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=4&annotation=XMW2TYCG))

“Our objective pushes messages which can not reduce the uncertainties in action-value functions of other agents close to the origin of the latent message space. This naturally gives us a hint on how to drop meaningless messages – we can order the message distributions according to their means and drop accordingly.” ([Wang et al., 2020, p. 5](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=5&annotation=JYG3FSQQ))

“we can make decisions in a bit-by-bit fashion and send messages with various lengths” ([Wang et al., 2020, p. 5](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=5&annotation=4K2R6ZU4))

“The results indicate that we can omit more than 80% of communication without significantly affecting performance. For comparison, we cut off messages in QMIX+TarMAC whose weights are 80% smallest and find that its performance drops significantly (Fig. 8)” ([Wang et al., 2020, p. 10](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=10&annotation=RCMJQ7RT))

“Empirical” ([Wang et al., 2020, p. 10](zotero://select/library/items/2A7LK9P5)) ([pdf](zotero://open-pdf/library/items/YH5IGXPJ?page=10&annotation=D9RAFKKU))