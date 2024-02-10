202402081826

Tags: #optimization 

# Frank Wolfe Algorithm
aka [[Conditional Gradient Algorithm]].

An alternative to [[Projected Gradient Descent]].


#### Algorithm:
Goal:
$$
\text{min}: f(x), \text{f is $\beta$-smooth}
$$
Differences between a projected GD and Frank Wolfe:
$$
\begin{flalign}
\text{Projected GD:}\ &x_{t+1} = \text{Proj}_{\chi} (x_t - \eta \nabla f(x_{t})) \\
\text{FW:}\ &y_t \in \text{argmin:} \nabla f(x_t)^Ty,\ \text{s.t.}\ y \in \chi \\
& x_{t+1} = (1 - \gamma_t)x_t + \gamma_t \cdot y_t
\end{flalign}
$$
With Frank Wolfe, at no point does $x_{t+1}$ move outside of the set, so there is no need to project back in.  $y_t$ belongs in $\chi$, $x_t$ belongs in $\chi$.

Frank Wolfe replaces projection (which could be a complicated operation) with linear minimization (which also could be complicated).  If linear optimization might be easy compared to projection, then Frank Wolfe could be a better option.

#### Theorem:
Let $f, \chi$ be convex, with f [[Beta-Smooth Convex]] in any arbitrary [[Norm]]:
$$
||\nabla f(x) - \nabla f(y)||_* \leq \beta \cdot ||x - y||
$$
Let $R = \text{diam} \chi = \text{sup}_{x, y \in \chi} ||x - y||$,
$\gamma_t = \frac{2}{t + 1}$
Then, the FW algorithm guarantees that $f(x_t) - f(x^*) \leq \frac{2 \beta R^2}{T + 1}$

Convergence is O($\frac{1}{T})$, which is equivalent to O($\frac{1}{\epsilon}$).

$\beta$ is the smoothness parameter in ANY norm of choice.

---
# References
