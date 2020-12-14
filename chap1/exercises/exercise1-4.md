# Learning from Exploration

Suppose learning updates occured after all moves, including exploratory moves. If the step-size parameter is appropriately reduced over time ( but not the tendency to explore ), then the state values would converge to a different set of probabilities. What ( conceptually ) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? 

Assuming that we do continue to make exploratory moves, which set of probabilities might be better to learn? Which would result in more wins?

---

It seems likely that when we do not learn from exploratory moves, the probability set is 0 for all possible moves with the exception of the first move made which will be 1. This is because when we do not learn from exploratory moves, the value of the next state would always be equal to the value of the current state just because the agent feels as if it only has one possible move. 

However, if we learn from exploratory moves, the probability set would be a bunch of random probabilities for each possible move that has been made thus far in the agent's lifetime. This is because a larger number of different moves has been played and each of them result in different states. As such, each state values are different.

If we do continue to make exploratory moves, the set of probability with a larger number of different probabilities would likely result in more wins overall as it is able to determine moves that may be more efficient that if the first set of probability, with all 0 except one 1, was learned.