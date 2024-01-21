202401201305

Tags: #optimization 

# Convex Set
A set is convex if for any line created by two points in the set is still contained in the set.

$C \subseteq \mathbb{R}^n$ is convex if:
$$
\begin{flalign}
&\forall x_1, x_2 \in C, \forall \theta \in [0,1],\\
&\theta x_1 + (1 - \theta)x_2 \in C
\end{flalign}
$$

It is similar to an [[Affine Set]] except that $\theta$ is constrained to be within $[0,1]$

---
# References
[Stanford | Lecture 2 | Convex Optimization](https://youtu.be/P3W_wFZ2kUo?t=204)