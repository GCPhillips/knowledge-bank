202312051942

Tags: #reinforcementlearning 

# Bellman Equation
Shows how adjacent [[State]]s are related to each other in value.  It is used in defining [[Value Function]]s.  The value of the state is for the given [[Policy]] $\pi$.

$$
v_{\pi}(s)\ \dot{=}\ \sum_a \pi(a|s)\sum_{s', r}p(s', r|s, a)[r + \gamma v_{\pi}(s')]
$$
$$
\forall\ s \in S
$$

#### Action Values
$$
q_{\pi}(s,a)\ \dot{=}\sum_{s'}\sum_r p(s', r|s, a)[r + \gamma \sum_{a'} \pi(a'|s') q_{\pi}(s', a'|s, a)]
$$

---
# References
