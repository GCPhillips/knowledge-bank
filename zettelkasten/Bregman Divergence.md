202402091719

Tags: #optimization 

# Bregman Divergence
For $\phi$ convex,
$$
D_{\phi}(x,y) \triangleq \phi(x) - \phi(y) - \nabla \phi(y)^T(x-y)
$$

![[Pasted image 20240209172313.png]]

#### Example:
$$
\begin{flalign}
\text{let}\ \phi(x) = \frac{1}{2}||x||_2^2 \\ \\
D_{\phi}(x,y) &= \frac{1}{2}||x||_2^2 - \left[\frac{1}{2}||y||_2^2 + y^T(x - y)\right] \\
&= \frac{1}{2}\left[||x||_2^2 - 2y^Tx - ||y||_2^2 + 2||y||_2^2\right] \\
&= \frac{1}{2}\left[||x||_2^2 - 2y^Tx + ||y||_2^2\right] \\
&= \frac{1}{2}||x - y||_2^2
\end{flalign}
$$

#### Properties:
$$
(\nabla\phi(x) - \nabla\phi(y))^T(x - z) = D_{\phi}(x,y) + D_{\phi}(z,x) - D_{\phi}(z,y)
$$
---
# References
