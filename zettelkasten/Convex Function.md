202401211223

Tags: #optimization 

# Convex Function
$f: \mathbb{R}^n \rightarrow \mathbb{R}$

#### Definition:

###### Definition 1
$f$ is convex if:
$$
\begin{flalign}
&\forall x_1, x_2 \in \mathbb{R}^n, \forall \lambda \in [0,1] \\
&f(\lambda x_1 + (1 - \lambda)x_2) \leq \lambda f(x_1) + (1 - \lambda)f(x_2))
\end{flalign}
$$
Equivalently ([[Jensen's Inequality]]):
$$
f(\mathbb{E}[X]) \leq \mathbb{E}[f(X)]
$$

The cord (line segment above the convex function) is the right-hand side of the function ($\lambda f(x_1) + (1 - \lambda)f(x_2)$).

###### Definition 2
Also, any tangent line at any point of the function will be below the function:
$$
f(y) \geq f(x) + \langle\nabla f(x), y - x\rangle
$$
or
$$
f(y) \geq f(x) + \langle g, y - x\rangle
$$
###### Definition 3
Finally, the [[Hessian Matrix]] is [[Positive Semidefinite]] (i.e. there should be a second derivative).  This property implies the second property:
$$
\nabla^2f(x) \geq 0
$$

#### Properties
If $f$ is convex, then the [[Subgradient]] (gradient) is [[Monotone]]:
$$
\begin{flalign}
\langle \nabla f(x) - \nabla f(y), x - y\rangle \geq 0 \\
\end{flalign}
$$
or, if it is not differentiable:
$$
\langle g_x - g_y, x - y\rangle \geq 0, \text{for $g_x \in \partial f(x), g_y \in \partial f(y)$}
$$

![[Pasted image 20240121122725.png]]

---
# References
Online Learning & Optimization - lecture 1.2.3 - Convex Functions - Definitions

[Wikipedia (Jensen's Inequality)](https://en.wikipedia.org/wiki/Jensen%27s_inequality)