202312060709

Tags: #reinforcementlearning 

# Optimal State-Value Function
A [[Value Function]].

Chooses the best state-value from a [[Policy]] given a state:

$$
v_*(s)\ \dot{=}\ \max_{\pi}v_{\pi}(s)
$$
There is always at least one policy that is greater than or equal to any other policy.


In terms of $q_*$, the value can be calculated by:

$$
v_*(s) = \max_{a \in A(s)} q_*(s,a),\ \ \text{for all } s \in S
$$

##### Bellman
A recursive function that uses the [[Bellman Equation]].
Take an optimal action and act optimally forever after that.

$$
v_*(s)\ =\ \max_a \sum_{s', r}p(s', r\ |\ s, a)[r + \gamma v_*(s')]
$$
##### Example
![[Pasted image 20231206165458.png]]
In the above example, the last sub-example (with [[Probabilistic Transition Function]]s, not [[Deterministic Transition Function]]s) has an [[Expectation]] of -4 for choosing $a_1$, and an expectation of +1 for choosing $a_2$, so $a_2$ is a better choice.


---
# References
