202402202159

Tags: #optimization 

# Affine Transformation
Using a linear transformation, convert an ill-conditioned matrix into a well-conditioned matrix.

$x = Ay$, 
A is [[Positive Semidefinite]] and invertible, and therefore:
$y = A^{-1}x$

Define:
$g(y) = f(Ay)$

then $f(x) = g(y)$.


By transforming the space and performing [[Gradient Descent]], the starting location might be the same but a different (and possibly shorter) path will be taken.  If the wrong affine transformation is taken, it could possibly lead to longer descent.

The transformation has the potential to decrease the [[Condition Number]], which is the main goal.  The best transformation is the one that makes the local condition number equal to 1.

If a matrix $M$ is symmetric with positive [[Eigenvalue]]s, then $M^{-1/2}$ is a symmetric matrix with positive eigenvalues.

---
# References
