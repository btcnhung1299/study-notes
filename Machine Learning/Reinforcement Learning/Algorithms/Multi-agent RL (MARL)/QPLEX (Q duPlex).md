# Annotations  
(23/06/2022, 08:41:08)

“in order to achieve scalability, existing MARL methods either limit representation expressiveness of their value function classes or relax the IGM consistency, which may suffer from instability risk or may not perform well in complex domains” ([Wang et al., 2021, p. 1](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=1&annotation=7W286Y6Y))

“This paper presents a novel MARL approach, called duPLEX dueling multi-agent Q-learning (QPLEX), which takes a duplex dueling network architecture to factorize the joint value function” ([Wang et al., 2021, p. 1](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=1&annotation=G3NCI7TF))

“duplex dueling network architecture to factorize the joint value function” ([Wang et al., 2021, p. 1](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=1&annotation=2IKDK9QA))

“QPLEX achieves a complete IGM function class” ([Wang et al., 2021, p. 1](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=1&annotation=T6PRFFJS))

“As shown by Wang et al. (2020a), the incompleteness of the joint value function class may lead to poor performance or potential risk of training instability in the offline setting (Levine et al., 2020)” ([Wang et al., 2021, p. 2](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=2&annotation=AQ3I7U3B))

“QPLEX introduces the dueling structure Q = V + A (Wang et al., 2016) for representing both joint and individual (duplex) action-value functions and then reformalizes the IGM principle as an advantage-based IGM” ([Wang et al., 2021, p. 2](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=2&annotation=DY5QYLLK))

“QPLEX takes advantage of a duplex dueling architecture to encode it into the neural network structure and provide a guaranteed IGM consistency” ([Wang et al., 2021, p. 2](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=2&annotation=UISZUH2P))

“we will first introduce advantage-based IGM, equivalent to the regular IGM principle, and, with this new definition, convert the IGM consistency of greedy action selection to simple constraints on advantage functions.” ([Wang et al., 2021, p. 3](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=3&annotation=DYJE6JIX))

“convert the IGM consistency of greedy action selection to simple constraints on advantage functions” ([Wang et al., 2021, p. 3](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=3&annotation=IPIBLLT2))

“A1(τ1, a1), . . . , arg max an ∈A An(τn, an) )” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=YJ5RTHPL))

“arg max a∈A Atot(τ , a) = arg max a1∈A A1(τ1, a1), . . . , arg max an∈A An(τn, an)” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=86KUCCSB))

“The advantage-based IGM and IGM function classes are equivalent” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=P3DS6P7P))

“One key benefit of using advantage-based IGM is that its consistency constraint can be directly realized by limiting the value range of advantage functions” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=V4M6TBT7))

“Atot(τ , a∗) = Ai(τi, a∗i ) = 0” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=CYGZ4HEK))

“Fact 1 enables us to develop an efficient MARL algorithm that allows the joint state-value function learning with any scalable decomposition structure and just imposes simple constraints limiting value ranges of advantage functions” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=QJG3RWXF))

“The overall architecture of QPLEX is illustrated in Figure 1, which consists of two main components as follows: (i) an Individual Action-Value Function for each agent, and (ii) a Duplex Dueling component that composes individual action-value functions into a joint action-value function under the advantage-based IGM constraint” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=FS78QMSE))

“Individual Action-Value Function is represented by a recurrent Q-network” ([Wang et al., 2021, p. 4](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=4&annotation=VSUTI5JG))

“a Transformation network module that incorporates the information of global state or joint history into individual action-value functions” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=2JYH6IGB))

“Dueling Mixing network module that composes separate action-value functions from Transformation into a joint action-value function.” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=SJPDBEQG))

“Vi(τ ) = wi(τ )Vi(τi) + bi(τ )” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=H2PGVIU5))

“where wi(τ ) > 0 is a positive weight. This positive linear transformation maintains the consistency of the greedy action selection and alleviates partial observability in Dec-POMDP (Son et al., 2019; Yang et al., 2020)” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=LHW5CDKQ))

“simple sum structure to compose the joint value” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=LCGBEV7B))

“Vtot(τ ) = Xn i=1 Vi(τ )” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=WJXJ97PP))

“To enforce the IGM consistency of the joint advantage and individual advantages” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=2CYSZ4EN))

“Atot(τ , a) = Xn i=1 λi(τ , a)Ai(τ , ai), where λi(τ , a) > 0” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=MCTUJGJY))

“The positivity induced by λi will continue to maintain the consistency flow of the greedy action selection” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=KL4GLW9U))

“learning of importance weights λi with joint history and action, QPLEX uses a scalable multi-head attention module” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=PV6Q7S88))

“Xn i=1 (λi(τ , a) − 1) Ai(τ , ai)” ([Wang et al., 2021, p. 5](zotero://select/library/items/ZWQSG6ER)) ([pdf](zotero://open-pdf/library/items/UN7VUB8D?page=5&annotation=KKFIJS2V))