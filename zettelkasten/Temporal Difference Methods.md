202312091439

Tags: #reinforcementlearning 

# Temporal Difference Methods
AKA TD Methods.

On each time step, the value estimation is updated.  The values used are the [[Reward]]s seen and estimated values of the next [[State]].

There is lower [[Variance]] compared to [[Monte Carlo Methods]] since updates are made on each time step.  However, there can be [[Bias]].

$TD(0)$ is the same as [[n-step Methods]] where $n == 1$ (1-step).

---
# References
