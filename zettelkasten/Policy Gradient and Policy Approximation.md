202312091652

Tags: #reinforcementlearning 

# Policy Gradient and Policy Approximation
$$
\nabla J(\theta) \propto \sum_s \mu (s) \sum_a q_{\pi}(s,a)\nabla \pi(a|s, \theta)
$$
$J(\theta)$ is a performance measure with respect to policy parameters $\theta$.  The goal is to maximize performance (use gradient *ascent*).

Parameterization of the policy could be in any way as long as $\pi(a|s, \theta)$ is differentiable.  A common approach is [[Softmax]]:

$$
\pi(a|s,\theta) = \frac{e^{h(s,a,\theta)}}{\sum_b e^(s,b,\theta)}
$$
The action preferences can be computed in different ways, for example a linear function:

$$
h(s,a,\theta) = \theta^T x(s,a)
$$

---
# References

Ch 13