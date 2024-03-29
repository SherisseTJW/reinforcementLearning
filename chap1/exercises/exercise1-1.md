# Self-play

Suppose, instead of playing against a random opponent, the reinforcement learning algorithm described in the Tic-Tac-Toe example played against itself, with both sides learning.

What would happen in this case? Would it learn a different policy for selecting moves?

--- 

It seems likely that in such a case, the agent would learn a different policy to select moves as it faces against an opponent which is likely choosing moves that are similar to it. Furthermore, as one agent learns a different policy, the other agent similarly learns a new policy and performs actions that the first would not have encountered before. 

Unlike if the agent plays against a human opponent, the human opponent is likely to make different moves at different times even if given the same state. As such, the agent may learn a different policy or determine that its current policy is the 'best' one if it continuously plays human opponents that do not make an optimal move.

By playing against another constantly learning agent, both agents would continuously learn from the each other in a cycle, as both agents choose more and more optimal moves. 

Thus, we may also be able to conclude that an agent that learns as it plays against another agent would be more accurate and well-trained than that of one that plays against a human opponent as it does not encounter any difficulties in selecting a policy due to human error.

However, in a relatively smaller environment such as Tic-Tac-Toe, where there is a limited number of possible moves at any one state, there is also likely a limit to the possible actions that each agent can take. After a period of time, a scenario whereby both agents perform the most optimal move may occur, which will likely result in a draw. In such a situation, the reward policy defined will affect what actions the agent continues to view as the 'best' move.