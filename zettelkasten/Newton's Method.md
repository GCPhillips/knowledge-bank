202401150714

Tags: #optimization #machinelearning 

# Newton's Method
A method for optimizing a linear function.

#### Steps:
1.) Initialize $\beta_0$
2.) Newton Update:
$$
\beta_{t+1} = \beta_t - \eta (\nabla^2f(\beta_t))^{-1}\nabla f(\beta_t)
$$
where $\beta_t$ is where we are after $t$ iterations, $\eta$ is the step size, $\nabla^2f(\beta_t)$ is the [[Inverse Hessian Matrix]], and $\nabla f(...)$ is the gradient of function $f$.

---
# References
