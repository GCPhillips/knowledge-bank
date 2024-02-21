202401150710

Tags: #optimization #machinelearning 

# Gradient Descent
A method for optimizing a linear function.

Has linear convergence.

#### Steps:
1.) Initialize $\beta_0$
2.) GD Update:
$$
\beta_{t+1} = \beta_t + \eta \nabla f(\beta_t)
$$
where $\beta_t$ is where we are after $t$ iterations, $\eta$ is the step size, and $\nabla f(...)$ is the gradient of function $f$.

#### Approximation:
$f(x + d) \approx f(x) + \nabla f(x)^T(d) + \frac{1}{2\eta}||d||_2^2$

#### Gradient Computations for $\epsilon$ accuracy:

$O((n \times \frac{\beta}{\alpha}) \log(\frac{1}{\epsilon}))$


#### Convergence Rate:
If $f$ is [[Beta-Smooth Convex]] and [[Alpha-Strong Convex]], then convergence rate is:
$$
O(\frac{\beta}{\alpha} \log \frac{1}{\epsilon})
$$
This is linear convergence (1 iteration = 1 digit of accuracy).

---
# References
