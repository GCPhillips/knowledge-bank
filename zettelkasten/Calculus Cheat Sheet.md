202401230745

Tags: #calculus

# Calculus Cheat Sheet
## Derivatives
For the following derivatives, assume that the functions are differentiable.

### Rules
###### [[Power Rule]]
$$
\frac{d}{dx}(x^n) = n x^{n-1}
$$
###### [[Product Rule]]
$$
(f(x)g(x))' = f'(x)g(x) + f(x)g'(x)
$$

###### [[Quotient Rule]]
$$
\left(\frac{f(x)}{g(x)}\right)' = \frac{f'(x)g(x) - f(x)g'(x)}{\left(g(x)\right)^2}
$$

###### [[Chain Rule]]
$$
\frac{d}{dx}(f(g(x))) = f'(g(x))g'(x)
$$

### Misc Derivative Operations
###### Misc

Let $c \in \mathbb{R}$
$$
\begin{flalign}
&\frac{d}{dx}(c) = 0 \\
\\
&(c f(x))' = c f'(x) \\
\\
&(f(x) \pm g(x))' = f'(x) \pm g'(x) \\
\\
&\frac{d}{dx}(a^x) = a^x \ln(a) \\
\\
&\frac{d}{dx}(e^x) = e^x \\
\\
&\frac{d}{dx}(\ln(x)) = \frac{1}{x}, x \gt 0 \\
\\
&\frac{d}{dx}(\ln(|x|)) = \frac{1}{x}, x \ne 0 \\
\\
&\frac{d}{dx}(\log_a(x)) = \frac{1}{x\ln(a)}, x \gt 0
\end{flalign}
$$

###### Matrix/Vector Derivatives

Let $x \in \mathbb{R}^n, b$ a constant scalar or [[vector]], $B$ a constant [[matrix]]
$$
\begin{flalign}
&\frac{d}{dx}(x^TB) = B \\
\\
&\frac{d}{dx}(x^Tb) = b \\
\\
&\frac{d}{dx}(x^Tx) = 2x \\
\\
&\frac{d}{dx}(x^TBx) = 2Bx \\

\end{flalign}
$$

### Examples

###### 1
$$
\begin{flalign}
\frac{d}{dx}\left(\frac{x}{5}\right) &\\
&\text{<factor out the constant>} \\
&= \frac{1}{5} \frac{d}{dx}(x) \\
&= \frac{1}{5}(1) \\
&= \frac{1}{5}
\end{flalign}
$$

---
# References
[Calculus Cheat Sheet PDF](https://tutorial.math.lamar.edu/pdf/calculus_cheat_sheet_all.pdf)
[Matrix Derivatives cheat sheet PDF](https://www.gatsby.ucl.ac.uk/teaching/courses/sntn/sntn-2017/resources/Matrix_derivatives_cribsheet.pdf)
[Matrix Cookbook PDF](https://www.math.uwaterloo.ca/~hwolkowi/matrixcookbook.pdf)