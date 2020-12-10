# Symmetries

Many tic-tac-toe positions appear different but are really the same because of symmetries. How might the learning process be amended to take advantage of this? In what ways would this change improve the learning process?

Now, think again.

Suppose the opponent did not take advantage of symmetries. In that case, should we? Is it true, then, that symmetrically equivalent positions should necessarily have the same value?

---

In the case whereby the states are symmetrical to each other, if an effort is made such that the states are continously symmetrical, it seems that the logical conclusion would be that the two states can be equated to each other. I.e. they have the same value function and reward signal and the same policy would have the exact same ending in both states. 

If the agent is able to understand such, the agent would likely take a shorter time to reach the same stage of its training then if the agent does not having this intrinsic understanding as it both reduces the number of explorations it takes and is able to perform more simulations on a given state, thus obtaining a stronger policy.


However, the problem lies in the fact that if effort is not given towards maintaining this symmetrical state, we cannot necessarily say that the two states are the same as the other as they do not have the same value function as future states are not necessarily similar to each other. 


As such, it seems wise to allow the agents to play against opponents that both take advantage of and do not take advantage of symmetries.