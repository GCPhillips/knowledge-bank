202401241942

Tags:

# Subgradient Method
$$
x_{t + 1} = x_t - \eta g_x
$$
where $g_x \in \partial f(x)$.

In other words, the update does not use a gradient since the function may not be differentiable, so it is replaced with an element of the subdifferential ($g_x$, where $g_x \in \partial f(x)$).

The method is not necessarily a descent method; $f(x_{t+1})$ might be strictly greater than $f(x_t)$.  However, the method *will* give an optimal solution.

### Subgradient Method for Lipschitz Convex Functions
###### Summary:
- If we plan to run for $T$ iterations, the best [[Step Size]] should be $\eta \approx \frac{1}{\sqrt{T}}$
- The error after $T$ iterations is $\approx \frac{1}{\sqrt{T}}$.  To have error $\epsilon$, we need $\approx \frac{1}{e^2}$ iterations. 

###### Method:
Let $f$ be convex.
Assume $\forall x, \forall g_x \in \partial f(x), ||g_x||_2 \leq G$

$$
\begin{flalign}
||x_{t+1} - x^*||_2^2 &= ||x_t - \eta g_t - x^*||_2^2 \\
&= ||x_t - x^*||_2^2 - 2\eta\langle g_t, x_t - x^*\rangle + \eta^2||g_t||_2^2 \\ \\
&\text{when you see something like $\langle g_t, x_t - x^*\rangle$,}\\
&\text{you should be thinking about definition of convexivity ($f(y) \geq f(x) + \langle g_x, y - x\rangle$)}. \\ \\
&\leq ||x_t - x^*||_2^2 - 2\eta(f(x_t) - f(x^*)) + \eta^2||g_t||_2^2 \\
&\leq ||x_t - x^*||_2^2 - 2\eta(f(x_t) - f(x^*)) + \eta^2G^2 \\ \\
&\text{rearrange the terms} \\ \\
2\eta(f(x_t) - f(x^*)) &\leq ||x_t - x^*||_2^2 - ||x_{t+1} - x^*||_2^2 + \eta^2G^2 \\
f(x_t) - f(x^*) &\leq \frac{1}{2\eta}\left(||x_t - x^*||_2^2 - ||x_{t+1} - x^*||_2^2\right) + \frac{\eta}{2}G^2 \\ \\
&\text{the portion in parantheses forms a telescoping sum} \\ \\
\frac{1}{T}\sum_{t=1}^T(f(x_t) - f(x^*)) &\leq \frac{1}{2\eta}\frac{1}{T}(||x_1 - x^*||_2^2 - ||x_T - x^*||_2^2) + \frac{1}{T}\sum_{t+1}^T\frac{\eta}{2}G^2 \\ \\
&\text{there is no $t$ on the last term, so the sum and fraction cancel out} \\ \\
\frac{1}{T}\sum_{t=1}^T(f(x_t) - f(x^*)) &\leq \frac{1}{2\eta}\frac{1}{T}(||x_1 - x^*||_2^2 - ||x_T - x^*||_2^2) + \frac{\eta}{2}G^2 \\ \\
&\text{since this is an inequality, the subtraction in the middle term can be dropped due to it not changing the result} \\ \\
\frac{1}{T}\sum_{t=1}^T(f(x_t) - f(x^*)) &\leq \frac{1}{2\eta}\frac{1}{T}(||x_1 - x^*||_2^2) + \frac{\eta}{2}G^2 \\
f(\frac{1}{T}\sum x_t) - f(x^*)) &\leq \frac{1}{2\eta T} R^2 + \frac{\eta}{2}G^2 \\ \\
&\text{let $\eta \approx \frac{1}{\sqrt{T}}$ to balance out the $\eta$ fractional terms.  Watch the youtube video around 20'} \\ \\

\end{flalign}
$$



---
# References
[3.4 Convergence Rates (Youtube)](https://youtu.be/R8kL8CKyz5I?si=RFcCW6DokaY8i8bW)
[Carnegie Mellon - sg-method](https://www.stat.cmu.edu/~ryantibs/convexopt/lectures/sg-method.pdf)
