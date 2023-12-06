202312061725

Tags: #reinforcementlearning 

# Discounted Return Value

$G_t$

is the return value following time $t$.

$$
G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots
$$
##### Example
Taken from homework 3.3

Suppose $\gamma = 0.5$ and the following sequence of rewards is received:
$R_1 = -1, R_2 = 2, R_3 = 6, R_4 = 3, R_5 = 2$, and 0 afterwards.  What are $G_0, G_1,\dots,G_5$?

To calculate $G_0$:
$$
G_0 = \gamma^0 R_1 + \gamma^1 R_2 + \gamma^2 R_3 + \gamma^3 R_4 + \gamma^4 R_5
$$

To calculate $G_3$:
$$
G_3 = \gamma^0 R_4 + \gamma^1 R_5
$$

---
# References
