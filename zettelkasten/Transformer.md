202310101348

Tags: #nlp #deeplearning 

# Transformer
A part of a model which can be a single layer or stacked with multiple other transformer blocks.

They're good at taking seemingly independent chunks and using [[Self-Attention]] to figure out an alignment between them.

Can be viewed as a transformation of a sequence of vectors into a sequence of [[Context]]-dependent vectors (similar to [[RNN]]s).

![[Pasted image 20231010141546.png]]

##### Architecture
[[Multi-Head Attention]] layer is fed into a [[FFNN]] layer.  There are [[Residual Connection]]s between them.  Most of the parameters are in the [[FFNN]] layer.

$$
FFN(x) = max(0, xW_1 + b_1)W_2 + b2
$$

##### Dimensions
**Vectors**: $d_{model}$
**Queries/keys**: $d_k$, always smaller than $d_{model}$
**Values**: separate dimension $d_v$, output is multiplied by $W^0$, which is $d_v \times d_{model}$ so we can get back to the $d_{model}$ before the residual

![[Pasted image 20231010141940.png]]

---
# References
https://www.youtube.com/watch?v=sLsUD-RcDqg
