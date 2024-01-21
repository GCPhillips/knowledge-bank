202401211223

Tags: #optimization 

# Convex Function
$f: \mathbb{R}^n \rightarrow \mathbb{R}$

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

Also, any tangent line at any point of the function will be below the function:
$$
f(y) \geq f(x) + <\nabla f(x), y - x>
$$

Another property:
A function is convex if:
$$
\begin{flalign}
\forall x, \exists g\ \text{s.t.} \\
f(y) \geq f(x) + <g, y - x>
\end{flalign}
$$

![[Pasted image 20240121122725.png]]

---
# References
Online Learning & Optimization - lecture 1.2.3 - Convex Functions - Definitions

[Wikipedia (Jensen's Inequality)](https://en.wikipedia.org/wiki/Jensen%27s_inequality)