202310081130

Tags: #nlp

# CKY Algorithm

An algorithm that uses [[Dynamic Programming]] to compute the most likely [[Tree]] given a [[Sentence]].

$$argmax_T\ \ \ P(T | x)$$
$$=argmax_T\ \ \ P(T, x)$$
Similar to the [[Viterbi Algorithm]] in that it builds a [[Tag]]/[[Sentence]] matrix, but a little more involved.  It predicts the tree structure instead of a sequence of tags.

Runtime for the algorithm is cubic.

![[Pasted image 20231008113718.png]]
##### Dynamic Programming
1.) Base Case: 
$T[i, j, X] = log P(w_i | X)$

2.) Recurrent Case: 
$T[i,j,X] = max_k\ max_{r:X -> X_1 X_2} \ log P(x -> X_1 X_2) + T[i,k,X_1] + T[k,j,X_2]$


---
# References
