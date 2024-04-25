202401150714

Tags: #optimization #machinelearning 

# Newton's Method
A method for optimizing a linear function.  It is [[Gradient Descent]] with the optimal [[Affine Transformation]].
Can be thought of as:
$$
\text{Newton} = \text{GD} + \text{Transformation}
$$
at each step, where transformation=[[Affine Transformation]].

Much faster than [[Gradient Descent]] and [[Accelerated Gradient Descent]].

Has quadratic convergence.

Newton's Method assumes $f(x)$ has 1st and 2nd order derivatives ([[Hessian Matrix]]).
#### Comparison with Gradient Descent:
Where the algorithm is slow is the inversion of the matrix, which is order $O(n^3)$, compared to [[Gradient Descent]] which uses vector addition only at order $O(n)$.  

[[Gradient Descent]] takes $O(n \cdot (\frac{\beta}{\alpha}) \cdot log (\frac{1}{\epsilon}))$ operations in order to get $\epsilon$-accuracy error.
Newton takes $O(n^3 \cdot \log \log \frac{1}{\epsilon})$.  As $n$ grows, $\log \log \frac{1}{\epsilon}$ has to be much smaller than $\log \frac{1}{\epsilon}$, which is already pretty small.

If you have a small problem and require very high accuracy, use Newton's Method.
If you have a large problem where $\epsilon$-accuracy isn't as big of a requirement, use [[Gradient Descent]].

#### Approximation:
$f(x + d) \approx f(x) + \nabla f(x)^T d + \frac{1}{2} d^T \nabla^2 f(x) d$

where $(\nabla^2 f(x))_{i, j} = \frac{\partial^2f}{\partial x_i \partial x_j}$

#### Algorithm Versions:
There are two variants of the algorithm
###### Damped:
Phase 1: used when not very close to the optimal solution.  [[Back Tracking Line Search]] is used to find the best step size.

$x_{t+1} = x_t - \eta(\nabla^2 f(x_t))^{-1} \nabla f(x_t)$
###### Undamped:
Phase 2: used when very close to the optimal solution.  This is where we get to the region of quadratic convergence.

$x_{t+1} = x_t - (\nabla^2 f(x_t))^{-1} \nabla f(x_t)$
(i.e., no $\eta$ for step size)

#### Steps:
1.) Initialize $\beta_0$
2.) Newton Update:
$$
\beta_{t+1} = \beta_t - \eta (\nabla^2f(\beta_t))^{-1}\nabla f(\beta_t)
$$
where $\beta_t$ is where we are after $t$ iterations, $\eta$ is the step size, $\nabla^2f(\beta_t)$ is the [[Inverse Hessian Matrix]], and $\nabla f(...)$ is the gradient of function $f$.

#### Convergence Rate:
Faster than [[Gradient Descent]].
$$
O(\log \log \frac{1}{\epsilon})
$$
This is quadratic convergence (1 iteration doubles digits of accuracy).

---
# References
