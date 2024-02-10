202402031004

Tags: #optimization 

# Proximal Gradient Descent
Also known as [[ISTA]] (Iterative Shrinkage-Thresholding Algorithm).

An optimization algorithm that solves a function in the form of a sum of a smooth component (see [[Beta-Smooth Convex]]) and a non-smooth component:
$$
f(x) = g(x) + h(x)
$$
where $g(x)$ is [[Beta-Smooth Convex]] and $h(x)$ is non-smooth.

#### Iterative Update:
$$
x_{t+1} = \text{prox}_{\eta h}(x_t - \eta \nabla f(x_t))
$$
Each iteration will require:
- evaluation of $\nabla f$
- evaluation of the $\text{prox}$ operator


#### Example:
The [[Lasso Regression]] function's first component is $\beta$-smooth, the second (the [[Regularization]] term) is not:
$$
f(x) = \left[\frac{1}{2}||Ax - b||_2^2 + \lambda||x||_1\right]
$$
The proximal operator:
$$
\text{prox}_{\eta f}(x) = \text{argmin}_u:||u||_1 + \frac{1}{2\eta}||u-x||_2^2
$$
where $u$ is the optimal solution (i.e. $0 \in \partial ||u||_1 + \frac{1}{\eta}(u-x)$)

---
# References
[YouTube](https://www.youtube.com/watch?v=sy4pRJ3g530)