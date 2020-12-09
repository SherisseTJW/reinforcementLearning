# Table of Contents
- [Table of Contents](#table-of-contents)
- [What is Reinforcement Learning?](#what-is-reinforcement-learning)
  - [Brief introduction](#brief-introduction)
  - [Supervised, Unsupervised or Neither?](#supervised-unsupervised-or-neither)
  - [Markov Decision Processes](#markov-decision-processes)
- [Challenges](#challenges)
  - [Exploration v Exploitation](#exploration-v-exploitation)

# What is Reinforcement Learning?

## Brief introduction

In itself, Reinforcement Learning is simultaneously a problem, a class of solution methods that would work well on the problem and the field that studies said problem and solution methods.

It is a computational approach to learning from interaction whereby the end goal is to maximise the numerical reward the agent receives and is much more focused on goal-directed learning from interaction as compared to other approaches to machine learning such as Neural Networks.

Like other approaches to machine learning, there are many layers to reinforcement learning. The simplest of cases are those whereby actions only directly affect the reward obtained at that point in time. However, if the agent is to be applied in a real-world scenario, it is accepted that actions at one point in time have an impact on the future. 

As such, trial-and-error search ( referring to exploration by the agent to determine the optimal action given a particular environment ) and delayed reward are some of the most important distinguishing features of Reinforcement Learning.

## Supervised, Unsupervised or Neither?

Reinforcement learning cannot be strictly classified as a Supervised or Unsupervised Machine Learning Problem. 

Supervised Learning refers to learning from a training set of labeled examples whereby there is a provided definite answer from the beginning. On the other hand, Unsupervised Learning refers to finding a structure or a pattern hidden within unlabelled data.

In Reinforcement Learning, the agent is not told which actions to take but instead discovers for itself which actions would yield the most reward through exploration. While finding a set pattern or structure could be useful in some Reinforcement Learning problems, this is not the end goal.

## Markov Decision Processes

The problem of Reinforcement Learning can be formalised using ideas from dynamical systems theory, more specifically, the optimal control of incompletely-known Markov Decision Processes.

More information can be found in [Chapter 3](../chap3) but the general idea is to simply capture the most important aspects of the real-world problem facing the learning agent as it interacts over time with its environment.

These aspects are:
1. Sensation
    - The learning agent must, to a certain extent, be able to sense the state of its environment
2. Action
    - The learning agent must be able to take actions that affect its current state
3. Goal
    - The learning agent must have a goal, or goals, related to its environment.

# Challenges

## Exploration v Exploitation