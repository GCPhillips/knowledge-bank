202401240821

Tags: #optimization 

# Lipschitz Constant
A concept that gives a value to the Lipschitz Continuity of a function.

The constant satisfies the inequality:
$$
||f(x) - f(y)|| \leq L||x - y||
$$
where $L$ is the constant.  In other words, it bounds the rate at which the gradient changes across the function's domain.

If a function has Lipschitz continuous gradients, then it is [[Beta-Smooth Convex]].  The constant, $L$, is sometimes marked as $\beta$ (related to [[Beta-Smooth Convex]]).

#### Bounds:
$$
|f(x) - f(y)| \leq L||x - y||
$$
If $f$ is convex:
$$
f(y) \geq f(x) + \nabla f(x)^T(y - x)
$$
Equivalently:
$$
|f(x) - f(y) \leq ||\nabla f(x)||_* \cdot ||x - y||
$$
where $||\cdot||_*$ is a [[Dual Norm]].


$f$ is L-Lipschitz w.r.t. an arbitrary [[Norm]] if $||\nabla f(x)||_* \leq L$:
$$
|f(x) - f(y) - \nabla f(y)^T(x - y) \leq \frac{\beta}{2}||x - y||^2
$$
where $||x - y||^2$ is an arbitrary norm.

#### Example
Given a quadratic function:
$$
f(x) = \frac{1}{2}x^TAx + b^Tx + c
$$
calculate the [[Hessian Matrix]] of $A$ and get the eigenvalues of that matrix.  For a quadratic function, the Hessian matrix is the [[Coefficient Matrix]] of the quadratic terms (which is $A$ in this example).

Compute the [[Eigenvalue]]s of $A$.  The Lipschitz Constant is the maximum eigenvalue.

The [[Step Size]] of a [[Gradient Descent]] method on this function could be the inverse of the Lipschitz Constant, $\frac{1}{L}$, or $\frac{1}{\lambda_{max}(A)}$

---
# References
