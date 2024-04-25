202402221913

Tags: #optimization 

# BFGS
The key idea is to approximate the Hessian (from [[Newton's Method]]) without requiring the expensive computation ($O(n^3)$ for the inversion operation).

#### Idea:
$$
f(x_k + d) \approx m_k(d)
$$
We would like to capture curvature information in $m_k$.

###### We require:

$m_{k+1}$ matches the gradient of $f$ evaluated at the last two iterations:

![[Pasted image 20240222193715.png]]

A fundamental part of BFGS is:
$$
B_{k+1} (x_{k+1} - x_k) = \nabla f(x_{k+1}) - \nabla f(x_k)
$$
Relabeling the values:
$$
B_{k+1}s_k = y_k
$$
which is the [[Secant Equation]].


#### Algorithm:
```
for k = 1, ..., T (or gradient is smaller than a threshold)
	d_k = -H_k * grad(f(x_k)) # d_k is the direction
	x_k+1 = x_k + eta_k * d_k = x_k - eta_k * H_k grad(f(x_k))
	s_k = x_k+1 - x_k
	y_k = grad(f(x_k+1)) - grad(f(x_k))
	H_k+1 =(I-rho_k * s_k * y_k^T) * H_k * (I-rho_k * y_k * s_k^T) + rho_k*s_k*s_k^T
```

---
# References
