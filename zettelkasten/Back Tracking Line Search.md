202402210824

Tags: #optimization 

# Back Tracking Line Search
Used in [[Newton's Method]] during the damped phase to find the best step size.

Fix $0 \lt \alpha \lt \frac{1}{2}, \beta \lt 1$.
Given this condition:
$$
f\left(x_t + \eta(\nabla^2 f(x_t))^{-1}\nabla f(x_t)\right) \leq f(x_t) - \alpha \cdot \eta\left(\nabla f(x_t)^T\nabla^2f(x_t)^{-1}\nabla f(x_t)\right)
$$
start with $\eta = 1$.  If not satisfied, $\eta \leftarrow \eta\beta$

---
# References
