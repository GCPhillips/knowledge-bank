202404201255

Tags: #onlinelearning 

# Linear Bandits
Algorithm that observes context $c_t \in C$ and plays an action based on it.  They're great for recommendation systems.

#### Modeling Reward
A [[Feature Map]] can be used to model the reward:

$\gamma(c,a) = \langle\theta^{\ast}, \psi (c,a)\rangle, \theta^{\ast} \in \mathbb{R}^d$
where $\psi$ is the feature mapping function.

$\theta^{\ast}$ is unknown, but actions are known.

Each action $A_t$ is a [[Unit Vector]], which effectively selects $\theta_i^{\ast}$ since it is a dot product of the two to get the reward, and noise is added to it ($\eta_t$).
#### Reward
$x_t = \gamma(C_t, A_t) + \eta_t$

#### Regret
$R_n(\pi, v) = \mathbb{E}\left[\sum_{t=1}^n \underset{a \in A_t}{\max} \gamma(C_t, a) - \sum_{t=1}^n x_t\right]$
The first term in the expected value is the best action that is known, the second term is the rewards calculated by the algorithm where only the context is known.
#### Example:
A website that has a context of user location, browsing history, etc. and chooses an ad (Action) based on the context.  The reward is if the user clicked the ad.



---
# References
