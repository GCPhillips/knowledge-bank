202402091600

Tags: #optimization 

# Mirror Descent

#### Background:
The update for $x$ in the [[Subgradient Method]]:
$$
x_{t+1} = x_t - \eta g_t
$$
is also equal to:
$$
x_{t+1} = \text{argmin}_x: f(x_t) + g_t^T(x - x_t) + \frac{1}{2\eta}||x - x_t||_2^2
$$
where the term $f(x_t) + g_t^T(x - x_t)$ is a [[Linear Approximation]] to $f$ at $x_t$,
and the term $\frac{1}{2\eta}||x - x_t||_2^2$ is a [[Proximity Term]], which prevents it from moving too far away from $x_t$.  Otherwise, minimizing the linear function only will keep "rolling downhill".

Since the argument being minimized is $x$, the other $x_t$ terms can be dropped:
$$
x_{t+1} = \text{argmin}_x: \eta g_t^Tx + \frac{1}{2}||x - x_t||_2^2
$$
The prox term is just the [[2-Norm]], which has spherical symmetry (the [[Unit Ball]]).  It penalizes symmetrically in all directions.

An issue with the [[Subgradient Method]] is that the steepest direction for descent might be away (almost perpendicular) from the true minimizing $x$.  Using the linear approximation helps move towards the true minimizing $x$.

Choosing a different [[Proximity Term]] to a different [[Norm]] gives a different algorithm that may be better.

#### Idea:
$$
\begin{flalign}
x_{t+1} &= \text{argmin}_x: \eta g_t^Tx + \cancel{\frac{1}{2}||x - x_t||_2^2} \\
x_{t+1} &= \text{argmin}_x: \eta g_t^Tx + D_{\phi}(x, x_t)
\end{flalign}
$$
where $D_{\phi}$ is the [[Bregman Divergence]].
If $\phi = \frac{1}{2}||\cdot||_2^2$, then we recover the usual [[Subgradient Method]].
If $\phi = \frac{1}{2}x^TQx, Q \neq I,$ then we get a different algorithm.

The key constants in the rate of convergence is the [[Lipschitz Constant]].

---
# References
