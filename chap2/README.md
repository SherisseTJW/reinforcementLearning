# Table of Contents

- [Table of Contents](#table-of-contents)
- [k-armed Bandit Problem](#k-armed-bandit-problem)
- [Action-value Methods](#action-value-methods)
  - [Sample-average Method](#sample-average-method)
  - [Action Selection Rule](#action-selection-rule)
    - [Greedy Selection (Exploitation)](#greedy-selection-exploitation)
    - [Near-greedy Selection (Exploitation & Exploration)](#near-greedy-selection-exploitation--exploration)
- [10-armed Testbed](#10-armed-testbed)

# k-armed Bandit Problem

Reduced to its simplest form, the k-armed Bandit Problem refers to a learning problem whereby the agent is faced repeatedly with *k* different possible actions whereby it has to choose one to perform. Afterwhich, it then obtains a numerical reward, that is chosen from a stationary probabiliti distributions, depending on the action chosen. The objective, like most other learning problems in Reinforcement Learning, is therefore to maximise the expected total reward over a time period.

An analogous way to look at it is also to imagine a doctor who has to prescribe different experimental treatments to a series of ill patients. In such a case, an action refers to the selection of a treatment and the reward refers to how well the patient responded to said treatment.

Today, the term "Bandit Problem" is sometimes used as a generalisation of the problem as we described above. All references to a Bandit Problem will, unless otherwise stated, refer to the following case (Take note of the following notations):

Each *k* action has an expected or mean reward, which will be called the *value* of the action that corresponds to it. The action selected on a particular timestep, *t* will be referred to as *A_t* and the corresponding reward as *R_t*. The estimated reward of an action *a* at a particular timestep *t* is also denoted as *Q_t(a)* where the closer *Q_t(a)* is to *q_***(a)*, the better.

The value then of an arbitrary action *a*, denoted as *q_***(a)*, is the expected reward given that *a* is selected:

![expectedReward_eqn](./img/expectedReward.PNG)

# Action-value Methods

Action-value Methods are the collective name for estimating the values of actions and using said values to make action selection decisions.

The simplest, and most instinctive way, to estimate the values of actions is by averaging the rewards actually received, i.e. taking the mean of the sum of rewards when *a* was taken previously, prior to the current timestep *t*. This is also called the Sample-average Method.

## Sample-average Method

The Sample-average Method got its name from the fact that each estimate is an average of the sample of relevant rewards. The formula is as follows:

![trueValue_eqn](./img/trueValue.PNG)

If the denominator is 0, i.e. *a* has never been selected prior to this, then we define *Q_t(a)* as some default value, such as 0. Conversely, as the denominator approaches infinity then, by the law of large numbers, *Q_t(a)* converges to *q_***(a)*.

Of course, this is merely one of the simplest estimation method and it is not necessarily the best one.

## Action Selection Rule

An action selection rule refers to, as its name suggests, a rule that helps the agent decide which action to take out of the *k* different options.

### Greedy Selection (Exploitation)

The simplest rule is, as expected, to merely select the action with the highest estimated value. Essentially, to move greedily.

![greedyActionSelection_eqn](./img/greedyActionSelection.PNG)

If there is more than one greedy action, meaning that maybe two or more actions have the same *Q_t(a)*, then a selection is made, usually arbitrarily, between all the greedy actions.

Regardless, greedy action selection always **exploits** the current knowledge that an agent may have in order to maximise its immediate reward. Little time is afforded to sampling apparently inferior actions, **exploring** if you will, even if they may lead to better states with larger state value functions.

### Near-greedy Selection (Exploitation & Exploration)

A simple improvement to a greedy action selection would be to set a small probability, *epsilon*, that will in a way, change the selection rule at that timestep to instead select randomly from among all actions independent of any action-value estimates.

Methods using the Near-greedy selection rule can also be referred to as *epsilon-greedy methods*.

An advantage of this selection method is that, as the number of steps increases and approaches the limit, every action will be sampled an infinite number of times which ensures that all *Q_t(a)* converges to their respective *q_***(a)* which in turn implies that the probability of selecting the optimal action converges to greater than 1-*epsilon*, that is, near certainty.

In layman's terms, this means that seeing as we sample each action a near infinite number of times, we obtain a better and better estimate of the value of each action and thus, we can say with greater and greater certainty that we are choosing the most optimal action every time as we know the true values of each action at each timestep.

# 10-armed Testbed