202310111957

Tags: #machinelearning

# Perceptron
An algorithm that is used for Binary [[Classification]] where the output is +1/-1, or True/False, or similar.

The order of the training examples have an effect on the outcome of the algorithm (for example, 100 epochs without shuffling could give a different weight parameter than 100 epochs with shuffling).

If the data is not linearly separable, some ways to make them separable are:
- make pairs of words [[Bigram]]
- make triplets of words [[Trigram]]
- make an entire sentence a feature instead of just a word
- use a nonlinear model, such as [[FFNN]]

#### Algorithm
Let $x$ and $y$ be a single training example and label respectively, $f(x)$ a feature extractor, and $w$ the weight to learn:

```
y_pred = w^T f(x)
if y_pred = y
	w = w
else if y = +1
	w = w + alpha f(x)
else if y = -1
	w = w - alpha f(x)
```

Usually the decision rule is similar to:
```
w^T f(x) > 0 ?
	predict +1
w^T f(x) <= 0?
	predict -1
```

#### Loss
$$
loss(x^{(i)}, y^{(i)}, w) = 
\begin{cases}
0\text{ if }w^Tf(x^{(i)})y^{(i)} \geq 0 \\
-w^Tf(x^{(i)})y^{(i)} \text{ otherwise }
\end{cases}
$$
---
# References
