202402091740

Tags: #optimization #linearalgebra 

# Dual Norm
For $||\cdot||$ (any norm), its dual is defined as:
$$
\begin{flalign}
||u||_* \triangleq \text{max}&: u^Tv \\
s.t.&: ||v|| \leq 1
\end{flalign}
$$

The dual-norm of the [[1-Norm]] is the [[Infinity-Norm]].
The dual norm of the [[2-Norm]] is the [[2-Norm]].
The dual norm of the [[Infinity-Norm]] is the [[1-Norm]].
#### Example:

###### 2-Norm:
Let $||\cdot|| = ||\cdot||_2$
$$
\begin{flalign}
(||u||_2)_* = \text{max} &: u^Tv \\
s.t.&: ||v|| \leq 1
\end{flalign}
$$
then the maximizer is $v^* = \frac{u}{||u||}$, the max value is $u^Tv^* = \frac{u^Tu}{||u||_2} = ||u||_2$
i.e., the [[2-Norm]] is its own dual norm (self-dual).

---
# References
