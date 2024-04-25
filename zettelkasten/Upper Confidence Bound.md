202312050710

Tags: #reinforcementlearning 

# Upper Confidence Bound
A form of [[Optimism]].

It determines which action to select (such as in [[Multi-Armed Bandit]]) based on the highest upper value.

$$
C\sqrt{\frac{var Q(a)}{N(a)}}
$$
where C is some constant, N(a) is the number of times action a was selected, Q(a) is the value of action a.

An alternative formula, [[UCB1]]:
$$
C\sqrt{\frac{log\ t}{N(a)}}
$$
where t is the time step.  The idea being, as iterations increase and an action is not selected, its upper bound increases so it will eventually be a greedy option to select which will update its mean and [[Variance]].  [[UCB1]] guarantees logarithmic [[Regret]].


### Algorithm:
For each time step $t$:
$$
A_t = \underset{1 \leq j \leq k}{\text{argmax}} U_j (t-1, \delta)
$$
where:
$$
\begin{flalign}
U_j &= \hat{\mu}_j (t-1) + \sqrt{\frac{2 \ln (\frac{1}{\delta})}{T_j (t-1)}} \\
T_j &= \text{total times arm $j$ was drawn up to and including iteration $t - 1$} \\
\hat{\mu}_j(t-1) &= \text{the empirical average of $\mu_j$ at iteration $t - 1$}
\end{flalign}
$$

---
# References
