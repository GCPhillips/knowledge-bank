202312061618

Tags: #reinforcementlearning 

# Optimal Action-Value Function
A [[Value Function]] for [[Action]]s.

Uses the [[Bellman Equation]].

$$
q_*(s, a)\ =\ \sum_{s', r} p(s', r\ |\ s, a)[r + \gamma \max_{a'}q_*(s', a')]
$$
This can also be rewritten as:
$$
q_*(s, a)\ =\ \sum_{s', r} p(s', r\ |\ s, a)[r + \gamma v_*(s')]
$$

and also, in terms of $v_*$:
$$
q_*(s,a) = \sum_{s' \in S^+}\sum_{r \in R} p(s', r|s, a)(r + \gamma v_*(s')),\ \ \ \text{for all }s \in S, a \in A
$$

This function makes action selection much simpler since the [[Expectation]] of the available actions can be selected instead of doing one-step planning with [[Optimal State-Value Function]].

---
# References
