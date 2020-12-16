# Near-greedy Action Selection

In *epsilon*-greedy action selection, for the case of two actions and *epsilon* = 0.5, what is the probability that the greedy action is selected?

---

Given that there are two actions, one being the greedy action and the other being the non-greedy action, the probability of the greedy action being selected is 0.5 + (0.5 * 0.5) = 0.75.

Breakdown:
1. In the case that we are selecting greedily, the greedy action will be selected 100% of the time.
2. In the case that we are not selecting greedily, the greedy action has a 50% chance of being selected.