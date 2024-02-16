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

**Changing the prox term changes the direction of descent.**

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

#### Mirror Map:
$\phi$ is called a "Mirror Map".

$\nabla \phi$ maps to a "dual space":
![[Pasted image 20240211143544.png]]

#### Algorithm:
$$
\begin{flalign}
x_{t+1} &= \underset{x \in \triangle}{\text{argmin}}: \eta g_t^Tx + D_{\phi}(x, x_t)
\end{flalign}
$$
where $\triangle$ is the simplex.

$x_{t+1}$ is the Bregman Projection of $y_{t+1}$ onto $\chi = \triangle$.
i.e., $x_{t+1} = \underset{x \in \triangle}{\text{argmin}}: D_{\phi}(x, y_{t+1})$
It is looking over all $x$ in the simplex, and finding that $x$ which minimizes the [[Bregman Divergence]] to $y_{t+1}$.

$y_{t+1}$ is given by: $\nabla \phi (y_{t+1}) = \nabla \phi (x_t) - \eta g_t$

$y_{t+1}^{(i)} = x_t^{(i)} \times e^{-\eta (\nabla f(x_t))_i}$

finally,
$x_{t+1} = \frac{y_{t+1}}{||y_{t+1}||_1}$



$\phi$ needs to be non-euclidean.  If it is equal to $\frac{1}{2}||\cdot||_2^2$, then the problem is exactly [[Subgradient Method]].

###### Choosing $\phi$:

$\phi(x) = \sum x_i \log x_i$

$\phi$ is 1-strongly convex on the simplex ($\triangle$) with respect to $||\cdot||_1$
This implies that $\rho = 1$.
$R^2 = D_{\phi}(x_1, x^*)$ if $x_1 = (\frac{1}{n}, \dots, \frac{1}{n})$ (the point sitting in the middle of the simplex).


###### Bounds:
$f(\frac{1}{T}\sum_{t=1}^T x_t) - f(x^*) \leq RL\sqrt{\frac{2}{\rho T}} = \sqrt{2} \times \sqrt{\frac{\log n}{T}}$
compared to subgradient descent: $\sqrt{\frac{n}{T}}$

---
# References
