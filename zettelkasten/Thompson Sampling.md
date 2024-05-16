202312051807

Tags: #reinforcementlearning #onlinelearning 

# Thompson Sampling
An implementation of [[Bayesian Algorithm]].

Has similar properties to [[Upper Confidence Bound]].

It fits a distribution of what is the likely value for a specific action.  For example, in [[Multi-Armed Bandit]], for action 2, there would be a [[Gaussian/Normal Distribution]] of the possible rewards for that action.

Overall, Thompson Sampling empirically seems to be the best.

##### Algorithm
1. Given samples $X_1, X_2, \dots, X_{t-1}$, update the prior distribution on the environment (i.e., maintain posterior distribution: $Q(\cdot | x_1, \dots, x_{t-1})$ using [[Bayes' Rule]] starting from the prior distribution $Q(\cdot)$)
2. Draw a sample from this posterior distribution: sample on instance $v_t = (v_{1,t}, v_{2,t}, \dots, v_{k,t})^T \sim Q(\cdot | x_1, \dots, x_{t-1})$
3. Play arm using the sample $v_t = (v_{1,t}, \dots, v_{k,t})^T$, $A_t = \underset{1 \leq j \leq k}{\text{argmax}}\ v_{j,t}$ and break ties as the genie policy (the environment instance).

---
# References
