202402221850

Tags: #optimization 

# Quasi Newton Methods
Tries to get accelerated convergence rate from [[Newton's Method]] but tries to minimize costs associated with it (inversion of a matrix) by finding other [[Affine Transformation]]s that could work.

[[BFGS]] is an example of a Quasi Newton method.

#### Idea:
$$
x_{t+1} = x_t - \eta \cdot H_t \cdot \nabla f(x_t)
$$
If $H_t$ is the [[Inverse Hessian Matrix]] of $f(x_t)$, then it is exactly [[Newton's Method]].
We can find an $H_t$ that is better than the identity matrix and less expensive than the inverse hessian matrix.

$H$ could be a rescale that gets closer to circular level sets (instead of elongated level sets, which is bad for descent methods).  

If we are only rescaling the axes of a symmetric matrix $A$, that means we are only updating the coordinate points via the diagonal (and the rest 0).  A diagonal matrix greatly simplifies the computation.  Then the Hessian can be:

$$
\begin{flalign}
H &= \begin{pmatrix}
\frac{\partial^2 f}{\partial x_1^2} & 0 \\
0 & \frac{\partial^2 f}{\partial x_2^2}
\end{pmatrix}^{-1} \\ \\
&= \begin{pmatrix}
\frac{1}{(\frac{\partial^2 f}{\partial x_1^2})} & 0 \\
0 & \frac{1}{(\frac{\partial^2 f}{\partial x_2^2})}
\end{pmatrix}
\end{flalign}
$$

This inversion computation can be computed in linear time.

**This only works if the elongation is aligned well with the coordinate axes**
ex: assume:
$$
\nabla^2 f = \begin{pmatrix}1 & 0.99 \\ 0.99 & 1\end{pmatrix}
$$
Then the condition is around 200.  Then, if $H$ is just taking the inverse of the diagonals:
$$
H = \begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix}^{-1} = I
$$
In this case, it is just [[Gradient Descent]].

---
# References
