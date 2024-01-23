202401221748

Tags: #linearalgebra #optimization 

# Taylor Approximation

$$
f(x) \approx f(x_0) + \langle \nabla f(x_0), x - x_0 \rangle
$$
Using [[Gradient Descent]] to approximate the [[Linear Function]]:
$$
\begin{flalign}
\text{at iteration t:} &\\
x_{t+1} &= \text{argmin}_x : f(x_t) + \langle \nabla f(x_t), x - x_t \rangle + \frac{1}{2\eta}||x - x_t||_2^2 \\
\text{take the derivative, set to 0:} &\\
&0 + \nabla f(x_t) + \frac{1}{2\eta}(x - x_t) = 0 \\
\implies &x_{t+1} = x_t - \eta \nabla f(x_t)
\end{flalign}
$$

---
# References
