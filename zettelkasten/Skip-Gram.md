202310121855

Tags: #nlp

# Skip-Gram
A method for word [[embedding]].

The input word is used to predict each [[Context]] one word at a time.  This is opposite of [[Continuous Bag-of-Words]], which predicts the word given the [[Context]](s).

A window size of $k$ is used to see how many words to skip in both directions.  $k=1$ implies the nearest neighbors are the words to use.

$$
P(context=y\:|\:word=x) = \frac{e^{v_x * c_y}}{\sum_{y' \in y}e^{v_x * c_{y'}}}
$$
If $v_y$ is similar to $c_y$, $y$ is likely to be in $x$'s context.

#### Input
A large corpus of [[Sentence]]s (this should be as much as possible for better training).

#### Output
[[vector]]s $v$ and $c$ for each word type $w$.

#### Hyperparameters
- Word vector dimension $d$ (around 50 - 300)
- Window size $k$

#### Issues
Performing matrix multiplications + softmax over $|V|$ is very slow to compute.  Dot-product is performed on **all** words in softmax.

---
# References
