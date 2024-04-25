202312051811

Tags: #reinforcementlearning 

# Regret
The expected ([[Expectation]]) loss after taking N actions due to the fact that the best action was not always chosen.  In other words, the loss in rewards.

$$
\text{Regret} = R_t(\pi, \nu) = \mathbb{E}[\sum_{s=1}^t X_s^{\ast}] - \mathbb{E}[\sum_{s=1}^t X_s]
$$
where $R_t$ is the time horizon, $\pi$ is the player policy, $\nu$ is the environment, the first term is the expected optimal reward until time $t$, the second term is the player's expected return at time $t$.

It can also be decomposed as a combination of expected total times of choosing an arm and the [[Suboptimality Gap]]:
$$
R_t(\pi, \nu) = \sum_{a \in A} \triangle_a(\nu) \mathbb{E}[T_a(t)]
$$

---
# References
