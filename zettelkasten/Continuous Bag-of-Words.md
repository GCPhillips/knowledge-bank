202310122002

Tags: #nlp 

# Continuous Bag-of-Words
Similar to the [[Skip-Gram]] [[embedding]], except the words are predicted from the [[Context]] (instead of the opposite).

It also uses a window to see far back and forward to use the contexts.

$$
P(w\:|\:w_{-1}, w_{+1}) = softmax(W(c(w_{-1}) + c(w_{+1})))
$$
#### Issues
Performing matrix multiplications + softmax over $|V|$ is very slow to compute.  Dot-product is performed on **all** words in softmax.

---
# References
https://www.youtube.com/watch?v=gpP-depOUwg
