202402021205

Tags: #optimization 

see: [[Beta-Smooth Convex]]
# Alpha-Strong Convex
A continuous and differentiable function (i.e. [[Convex Function]]) is $\alpha$-strongly convex if 
$g(x) = f(x) - \frac{\alpha}{2}||x||_2^2$ is convex.

It is the 2nd definition of a [[Convex Function]] with a term added to it:
$$
f(y) \geq f(x) + \langle \nabla f(x), y-x \rangle + \frac{\alpha}{2}||y-x||_2^2
$$

Strong convexivity in a function leads to faster rates of convergence during optimization.


---
# References
