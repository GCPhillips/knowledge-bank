202402151858

Tags: #optimization #machinelearning 

# Reducing Variance by Recentering
Variance can be reduced by recentering the subgradient.

For any two points $x, z$:
$$
\begin{flalign}
\tilde{g}(x) &= \nabla f_I(x) - (\nabla f_I(z) - \nabla f(z)) \\ \\
\mathbb{E}_I\left[\tilde{g}(x)\right] &= \mathbb{E}_I\left[\nabla f_I(x)\right] - (\mathbb{E}_I\left[\nabla f_I(z)\right] - \nabla f(x)) \\
&= \nabla f(x) - \nabla f(z) - \nabla f(z) \\
&= \nabla f(x)
\end{flalign}
$$
where $I = \text{uniform}(1, \dots, n)$.

[[Stochastic Variance Reduced Gradient Descent]] focuses on this.

---
# References
