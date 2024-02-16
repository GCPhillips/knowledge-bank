202402110946

Tags: #optimization 

# Projected Gradient Descent
[[Gradient Descent]] with a projection back onto the [[Convex Set]].  It is a specific case of [[Proximal Gradient Descent]].

$$
x_{t+1} = \text{proj}_X(x_t - \eta \nabla f(x_t))
$$

$\text{proj}_X (\cdot)$ is called the Euclidean Projection Operator:
$$
\begin{flalign}
\text{proj}_X(x_0) &= \underset{x \in X}{\text{argmin}} || x - x_0 ||_2 \\
&= \underset{x \in X}{\text{argmin}} \tfrac{1}{2} || x - x_0 ||_2^2
\end{flalign}
$$
In other words, it finds the closest $x$ that is in the set $X$.

#### Algorithm:
1. compute the direction from the gradient: $-\nabla f(x_t)$
2. take a step in that direction: $y_{t+1} = x_t - \eta \nabla f(x_t)$
3. project back onto the set:
$$
x_{t+1} = \underset{x \in X}{\text{argmin}} \tfrac{1}{2} || x - y_{t+1} ||_2^2
$$

#### Convergence:
If $f$ is [[convex]] and L-Lipschitz (see [[Lipschitz Constant]]):
$$
O\left(\frac{1}{\sqrt{t}}\right)
$$
If $f$ is [[convex]] and [[Beta-Smooth Convex]] (i.e. like [[Gradient Descent]]):
$$
O\left(\frac{1}{t}\right)
$$
however, this depends on how complex the projection is.


(pg. 19 in CVX_PGD.pdf has proof)

---
# References
[CVX_PGD.pdf](https://angms.science/doc/CVX/CVX_PGD.pdf)