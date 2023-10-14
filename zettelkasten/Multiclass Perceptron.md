202310132322

Tags: #machinelearning 

# Multiclass Perceptron
A [[Classification]] problem based on [[Perceptron]] except there are multiple classes to predict.

#### Weights
##### Different Weights
There are a different set of weights per class (*this is typically used*).

$w_y^T \cdot f(x)$

For example:

```
w_health  = [1 0 0]
w_sports  = [0 1 0]
w_science = [1 1 0]
```

##### Different Features
Weights per class are concatenated into one [[vector]].

$w^T \cdot f(x, y)$
where $y$ is the hypothesized value.

For example:

```
f(x, y = health)  = [1 1 1 0 0 0 0 0 0]
f(x, y = sports)  = [0 0 0 1 1 1 0 0 0]
f(x, y = science) = [0 0 0 0 0 0 1 1 1]
```

#### Algorithm
This algorithm is for *Different Weights*:
$$
\begin{flalign*}
&\text{for t in epochs} \\
&\quad \text{for i in data} \\
&\quad \quad y_{pred} = argmax_y\:w_y^T \cdot f(x) \\
&\quad \quad \text{if } y_{pred} \neq y^{(i)} \\
&\quad \quad \quad w_{ypred} \leftarrow w_{ypred} - \alpha f(x) \\
&\quad \quad \quad w_{y^{(i)}} \leftarrow w_{y^{(i)}} + \alpha f(x) \\
\end{flalign*}
$$
This algorithm is for *Different Features*:
$$
\begin{flalign*}
&\text{for t in epochs} \\
&\quad \text{for i in data} \\
&\quad \quad y_{pred} = argmax_y\:w_y^T \cdot f(x) \\
&\quad \quad \text{if } y_{pred} \neq y^{(i)} \\
&\quad \quad \quad w \leftarrow w + \alpha f(x, y^{(i)})
\end{flalign*}
$$

---
# References
