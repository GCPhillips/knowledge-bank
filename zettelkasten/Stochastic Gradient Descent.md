202402151821

Tags: #optimization #machinelearning 

# Stochastic Gradient Descent
Goal:
$$
\underset{s.t. x \in \chi}{\min f(x)}
$$

Instead of regular [[Gradient Descent]], or an element of a subdifferential, replace with the expected value over any randomness that is an element of the subdifferential:
$$
\begin{flalign}
x &\rightarrow \cancel{\nabla f(x)\ \text{or}\ g_x \in \partial f(x)} \\
&\rightarrow \tilde{g}_x: \mathbb{E}[\tilde{g}_x] \in \partial f
\end{flalign}
$$
#### Theorem:
Suppose that $x^*$ exists, and $\mathbb{E}[||\tilde{g}_x||^2||] \leq G^2,\ \forall x$
SGD algorithm: $x_{t+1} = x_t - \eta \tilde{g}_x$
then:
$$
\mathbb{E}\left[f(\frac{1}{T}\sum x_t)\right] - f(x^*) \leq \frac{R\cdot G}{\sqrt{T}}
$$
where $R^2 \geq \mathbb{E}[||x_1 - x^*||_2^2]$

#### Algorithm (mini-batch):
Let $B = f_{i_1}, f_{i_2}, \dots, f_{i_B}$
$$
x_{t+1} = x_t - \eta \frac{1}{B} \sum_{j=1}^B \nabla f_{i_j}(x_t)
$$
where $f_{I}$ is a uniform distribution of $f$ (equal odds of choosing an $f$).

Further analysis to show that the expected value after $\eta$ is equivalent to the gradient of $f$ at $x_t$:
$$
\begin{flalign}
\mathbb{E}\left[\frac{1}{B}\sum_{j=1}^B \nabla f_{I_j}(x_t)\right] &= \frac{1}{B}\sum_{j=1}^B\mathbb{E}\left[ \nabla f_{I_j}(x_t)\right] \\
&= \frac{1}{B}\sum_{j=1}^B \nabla f(x_t) \\
&= \nabla f(x_t)
\end{flalign}
$$

The advantages of mini-batch:
- reduction in [[Variance]] (see [[Reducing Variance by Recentering]])
- parallelizable

Disadvantages:
- more work ($B$ times more) per iteration of the algorithm
- still can't exploit self-tuning in case when $f$ is smooth (the gradient goes to 0 as we get closer to $x^*$ (optimal solution))


#### Gradient Computations for $\epsilon$ accuracy:

$O\left(\dfrac{1}{\alpha \epsilon}\right)$


---
# References
