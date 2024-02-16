202402151906

Tags: #optimization #machinelearning 

# Stochastic Variance Reduced Gradient Descent
Great for problems that are ill-conditioned (see [[Condition Number]])
#### Algorithm:


![[Pasted image 20240215190942.png]]

The inner loop is just [[Stochastic Gradient Descent]] (the same computational effort)
- we just need to compute $\nabla f_I (x_t)$; $y_k$ does not change.
The outer loop requires a full computation of the gradient at $y$.

#### Key Lemma:

The [[Variance]] of our stochastic gradient goes to 0 as we approach the optimal solution.

Let $f_1, \dots, f_n$ be $\beta$-smooth, I ~ uniform$[n]$.
then:
$$
\mathbb{E}_I\left[||\nabla f_I(x) - \nabla f_I(x^*)||_2^2\right] \leq 2\beta (f(x) - f(x^*))
$$

#### Step size:
If the step size $\eta = \frac{1}{10 \times \beta}$ and the inner loop size is $T = 10 \times (\frac{\beta}{\alpha})$, after s + 1 iterations of the outer loop:
$$
\mathbb{E}f(y^{s+1}) - f(x^*) \leq 0.9^s (f(y^{(1)}) - f(x^*))
$$
The key features of this:
- Linear convergence
- $\frac{\beta}{\alpha}$ does not appear in the convergence rate (i.e. the number of outer loops needed to converge does not depend on it)

#### Gradient Computations for $\epsilon$ accuracy:

$O((n + \frac{\beta}{\alpha}) \log(\frac{1}{\epsilon}))$

---
# References
