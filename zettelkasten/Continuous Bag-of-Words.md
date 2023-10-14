202310122002

Tags: #nlp 

# Continuous Bag-of-Words
Similar to the [[Skip-Gram]] [[embedding]], except the words are predicted from the [[Context]] (instead of the opposite).

It also uses a window to see far back and forward to use the contexts.

*"the local context is computed as an average of embeddings for words in the immediate neighborhood $m - h, m - h + 1, \dots, m + h - 1, m + h$"* - **Eisenstein**

#### Approximation to Optimize
$$
\begin{flalign*}
log p(w) &\approx \sum_{m=1}^M log\:p (w_m\:|\:w_{m-h}, w_{m-h+1},\dots,w_{m+h-1}, w_{m+h}) \\
&= \sum_{m=1}^M log\:\frac{exp(u_{w_m} \cdot v_m)}{\sum_{j=1}^V exp(u_j \cdot v_m)} \\
&= \sum_{m=1}^M u_{w_m} \cdot v_m - log\sum_{j=1}^V exp(u_j \cdot v_m)
\end{flalign*}
$$
where:
- $u_i \rightarrow$ the word at $i$
- $v_j \rightarrow$ the context at $j$
#### Issues
Performing matrix multiplications + softmax over $|V|$ is very slow to compute.  Dot-product is performed on **all** words in softmax.

---
# References
https://www.youtube.com/watch?v=gpP-depOUwg

Eisenstein, pg 334