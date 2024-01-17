202401161816

Tags: #optimization #machinelearning 

# Lasso Regression
An optimization problem.  Also known as [[L1 Regularized Regression]].
Similar to [[Ridge Regression]], tries to find a linear relationship between data $x$ and labels $y$.

This is not used when columns are nearly co-linear (use [[Ridge Regression]] for that).  This is useful when $\beta$ is [[Sparse]] or nearly sparse.

$$
x^T\beta \approx y
$$
The goal:
$$
\text{minimize}: \frac{1}{n}\sum_{i=1}^n(x_i^T\beta - y_i)^2 + \lambda \sum|\beta_i|
$$
or:
$$
\text{minimize}: \frac{1}{n}||X\beta - y||_2^2 + \lambda||\beta||_1
$$
where $||\beta||_1$ is the [[1-Norm]] of $\beta$.

#### Second Term
The second term in the equation, $\lambda||\beta||_1$, is the sum of the absolute values of $\beta$.  Which means, **it is not differentiable**.  It also means there is no [[Hessian Matrix]] (if it doesn't have a 1st order derivative, then it won't have a 2nd order derivative).  This means [[Newton's Method]] can't be used since it uses the [[Inverse Hessian Matrix]].


#### Methods
The algorithm of choice is [[Proximal Gradient Method]] since it converges much faster than [[Sub-Gradient Method]] (which doesn't converge fully; it bounces around the convergence area).


---
# References
