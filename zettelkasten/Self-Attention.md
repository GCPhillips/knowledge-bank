202310102227

Tags: #nlp

# Self-Attention
A type of [[Attention]] where the word/vector in a sequence takes on the role of both **key** and **query** at the same time.

It produces a square attention matrix of dimensions $|input|\times|input|$.
It computes a [[Context]]ualized encoding for each word, preserving the length of the sequence.

[[Softmax]] is applied to give a probability distribution, which represents how much attention should be given to each element in the sequence.
#### Dimensions
$$
Q = |seq| \times d
$$
$$
K = |seq| \times d
$$
#### Formula
$$
self\:attention = softmax\left(\frac{QK^T}{\sqrt{d_k}}\right)
$$
$$
Q = EW^Q
$$
$$
K = EW^K
$$
$$
V = EW^V
$$
---
# References
