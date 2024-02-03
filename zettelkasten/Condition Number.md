202402021233

Tags: #optimization 

# Condition Number
A value that is used to quantify how sensitive a mathematical problem is to changes or errors in its input data.

In optimization, this is typically represented as $k = \frac{\beta}{\alpha}$, where $\beta$ is the largest [[Eigenvalue]] and $\alpha$ is the smallest [[Eigenvalue]].

A condition number at or very close to one implies that the problem is extremely well-conditioned; it implies the curvature of the function is very uniform across all directions.  The uniformity means the [[Hessian Matrix]] of the function has [[Eigenvalue]]s that are all close in magnitude.
As the condition number increases (insinuating a larger $\beta$ than $\alpha$) then it becomes more ill-conditioned.

---
# References
