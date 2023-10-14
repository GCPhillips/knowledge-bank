202310140909

Tags: #nlp 

# Lexicalization
A method for parsing [[Probabilistic Context-Free Grammar]]s.  Each grammar symbol is annotated with its head word.

For example:
The last word of an NP before a preposition is typically the head.

![[Pasted image 20231014095819.png]]

The parsers are incredibly hard to build.
#### Requirements
Three problems need to be solved:

1. identifying the heads of all constituents in a treebank
2. parsing efficiently while keeping track of the heads
3. estimating the scores for lexicalized productions

---
# References
Eisenstein, pg 245
https://www.youtube.com/watch?v=f1o1_bPWzM0