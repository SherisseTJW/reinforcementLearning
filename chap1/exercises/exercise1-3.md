# Greedy Play

Suppose the Reinforcement Learning player was greedy, that is, it always played the move that brought it to the position that it rated the best. Might it learn to play better, or worse, than a non-greedy player? What problems might occur?

---

It is likely that if the agent was greedy, the agent would perform better, i.e. receive a larger reward, than a non-greedy player initially. However, after a number of time steps, the non-greedy player would likely start to perform better than the greedy player as the non-greedy player performed more explorations and thus was able to discover actions that led to either a larger immediate reward or had a larger value, i.e. the action led to greater rewards in later time steps.

Additionally, a greedy player would likely stagnate quite quickly as it does not perform any explorations and thus, is likely to perform the same moves over and over again as a move that has already been performed once would likely have a larger reward signal than that of a move that has never yet been performed. As such, it is unlikely that for multiple lifetimes, the greedy agent would ultimately receive the same total reward at the end of each run.