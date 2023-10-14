202310140936

Tags: #nlp

# Horizontal Markovization
A [[Markovization]] technique for maintaining context in a parse tree.  It is a [[Binarization]] technique.

The amount of context remembered can be adjusted.

For example:
$h=\infty$  means remember everything
$h = 0$ means there is no context remembered
$h = 1$ means remember the previous context

It is "horizontal" since the context remembered is in the horizontal plane (i.e. it isn't the parent nodes remembered but the other head nodes in the same tree level).

![[Pasted image 20231014095125.png]]

---
# References
