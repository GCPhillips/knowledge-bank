202310081339

Tags: #nlp 

# Smoothing
A pre-processing normalization technique where counts are added to a [[Transition Matrix]] in a [[Hidden Markov Model]] to avoid 0 values.  This smooths the distribution.

$$\begin{pmatrix}
0 & 3 & 0 \\
0 & 0 & 3
\end{pmatrix}\rightarrow
\begin{pmatrix}
1 & 3 & 1 \\
1 & 1 & 3
\end{pmatrix}$$ 
---
# References
