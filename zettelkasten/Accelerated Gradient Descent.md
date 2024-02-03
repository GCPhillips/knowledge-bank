202402021228

Tags: #machinelearning #optimization 

# Accelerated Gradient Descent
Given an [[Alpha-Strong Convex]] and [[Beta-Smooth Convex]] [[Convex Function]]:

Initialize $x_1 = y_1 = x_{init}$
$y_{t+1} = x_t - \frac{1}{\beta} \nabla f(x_t)$
$x_{t+1} = \left (1 + \frac{\sqrt{k} - 1}{\sqrt{k} + 1)}\right)y_{t+1} - \left (\frac{\sqrt{k} - 1}{\sqrt{k} + 1)}\right)y_t$

where $\frac{1}{\beta}$ is the step size based on the smoothness parameter, $\frac{\sqrt{k} - 1}{\sqrt{k} + 1}$ is the [[Condition Number]] of the function.

This is a function of the past two iterates, which is where [[Momentum]] comes in.


#### Algorithm:
Gradient Update:
$$
x^+ = x - \eta \nabla f(x)
$$
Momentup Update:
$$
d_{t} = \gamma_{t}(x_{t} - x_{t-1})
$$
Gradient Descent Algorithm:
$$
x_{t+1} = (x_t)^+
$$
Nesterov Acceleration:
$$
\begin{flalign}
x_{t+1} &= (x_{t} + d_{t})^+ \\
&= x_t + d_t - \eta \nabla f(x_t + d_t)
\end{flalign}
$$

---
# References
