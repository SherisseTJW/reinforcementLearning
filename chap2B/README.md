# Table of Contents

- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Tracking Non-stationary Problems](#tracking-non-stationary-problems)
  - [Constant step-size parameter](#constant-step-size-parameter)

# Introduction

In the first part of this chapter, we went through different action-value methods and action selection rules that we can apply to a stationary problem to ensure that our Reinforcement Learning agent is able to reach its goal effectively. However, most real-world problems are not stationary and as such, if we want to learn how Reinforcement Learning can actually be applied in a real-world scenario, we have to know how to deal with non-stationary problems.

# Tracking Non-stationary Problems

When dealing with non-stationary problems, we should give more weight to recent rewards rather than long-past rewards. This will thus allow us to get a better understanding of the current true value of the reward of each action for each timestep.

One of the most popular ways to do this is to use a constant step-size parameter.

## Constant step-size parameter

![Constant Step-size Parameter eqn](./img/constantStepSizeParameter_updateRule.PNG)

*Take note that the step-size parameter &alpha; &#8712; (0,1] is constant* 

This also results in *Q<sub>n+1</sub>* being a weighted average of past rewards and the initial estimate *Q<sub>1</sub>*

![Constant Step-size Parameter Weighted Average](./img/constantStepSizeParameter_weightedAvg.PNG)