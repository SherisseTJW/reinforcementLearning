# Bandit example

Consider a *k*-armed Bandit Problem with *k* = 5 actions, each denoted 1, 2, 3, 4 and 5. 

Apply to this problem a bandit algorithm using *&epsilon;*-greedy action selection where the sample-average action-value estimates and initial estimates for *Q<sub>1</sub>(a)* = 0 for all *a*.

Now, suppose that the initial sequence of actions and rewards are:
* *A<sub>1</sub>* = 1, *R<sub>1</sub>* = -1 
* *A<sub>2</sub>* = 2, *R<sub>2</sub>* = 1 
* *A<sub>3</sub>* = 2, *R<sub>3</sub>* = -2
* *A<sub>4</sub>* = 2, *R<sub>4</sub>* = 2
* *A<sub>5</sub>* = 3, *R<sub>5</sub>* = 0 

On some timesteps, the *&epsilon;* case may have occurred, causing an action to be selected at random. On which time steps did such an occurrence definitely happen and on which time steps could this possibly have happened?

---

*In order to answer the above questions, we first make the assumption that there is no noise in the reward, i.e. reward variance = 0.*

The only time step whereby the *&epsilon;* case will definitely occur is on the first time step. This is because all the actions have the same initial estimate of 0. In this case, as the agent sees that all the actions have the same action-value estimate, it will pick an action arbitrarily, aka. it **explores**.

There are 3 scenarios whereby the *&epsilon;* case could possibly occur on any other timestep.
1. When the *&epsilon;* probability occurs
2. On the second time step
3. On the third time step
4. If the agent continuously picks *A<sub>5</sub>* and has not yet selected either *A<sub>2</sub>* or *A<sub>4</sub>*

The first scenario is fairly self-explanatory so I am just going to skip over that. Please read the [notes](../README.md) if you don't understand why this scenario will result in an *&epsilon;* case.

For the second scenario, the *&epsilon;* case may also occur on the second timestep if the agent picks *A<sub>1</sub>*, *A<sub>3</sub>* or *A<sub>5</sub>*. This is because the reward value for these 3 actions are smaller than or equal to 0. As such, the agent will see that the other 4 actions, i.e. the other 2 actions not chosen between *A<sub>1</sub>*, *A<sub>3</sub>*, *A<sub>5</sub>* as well as the other 2 actions, *A<sub>2</sub>* and *A<sub>4</sub>*, have the same action-value estimate of 0. As such, it will pick between these 4 actions arbitrarily.

The third scenario occurs when on the second timestep, the agent picks another action between *A<sub>1</sub>*, *A<sub>3</sub>* or *A<sub>5</sub>*. The same thing will occur as in the second scenario and the agent will pick between the remaining 3 actions arbitrarily.

With regards to the fourth scenario, this is because if the agent continously picks *A<sub>5</sub>*, which has a reward of 0, it sees that there are 3 actions with an action-value estimate of 0. As such, it will continuously pick between these 3 actions, *A<sub>5</sub>*, *A<sub>2</sub>* and *A<sub>4</sub>* arbitrarily until it picks either *A<sub>2</sub>* or *A<sub>4</sub>*.

Once the agent has picked either of *A<sub>2</sub>* or *A<sub>4</sub>*, the only case whereby the *&epsilon;* case will possibly occur is if the first scenario happens.