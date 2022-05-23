Structure:
1. What is reinforcement learning?
3. How to describe a problem in reinforcement learning? What are elements in reinforcement learning?
5. Why some problems are casted and solved as reinforcement learning?
6. What are some good resources to learn about reinforcement learning?
7. How they solve the problems with reinforcement learning?
8. Why are there many algorithms in reinforcement learning?
9. What are not have been covered?

---

## Introduction
Reinforcement learning is a learning paradigm in which our ultimate purpose is to maximise our reward. Typical benchmark in reinforcement learning involve game-playing in which you want to earn as many points as possible. Therefore, when reading a paper in reinforcement learning, you will almost always find the graph in which the efficiency of an algorithm is measured in the amount of returns they achive, the higher the better.

Mathematically, reinforcement learning problem can be formulated using Markov Decision Process (MDP). A MDP is described by 5-element tuple:
$$\langle \mathcal{S}, \mathcal{A}, R, P, \gamma \rangle$$

Let imagine you are playing the game Pong (attached an image). The game is regarded as an environment.
The first element $\mathcal{S}$ is the set of states $s \in \mathcal{S}$ that describes a "static image", or state of the environement at a timestep.
The second element $\mathcal{A}$ is the set of actions that we, as a player, can take during the game. Let assume this set is fixed during the course of the game.
The third element $R$ is the reward function that will generate/give us a reward $R_{t+1}$ at timestep $t$reward $R