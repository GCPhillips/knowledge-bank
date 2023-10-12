202310112056

Tags: #machinelearning 

# Logistic Regression
Maps a real number to a probability (i.e. predicts a value between 0-1).

Used for [[Classification]] problems where the probability of the classification is needed (for example, "there is .72 probability (72%) this picture contains a dog").

The goal during training is to maximize the likelihood of seeing the results given the input data (or equivalently, minimize the negative log-likelihood):

$$
\prod_{i=1}^D P(y^{(i)}\:|\:x^{(i)})
$$
Log-Likelihood:
$$
\rightarrow max_w \sum_{i=1}^D log\:P(y^{(i)}\:|\:x^{(i)})
$$
Negative Log-Likelihood:
$$
\rightarrow min_w \sum_{i=1}^D\:-log\:P(y^{(i)}\:|\:x^{(i)})
$$
Note: $P(y|x)$ is what the *model* assigns to class $y$.
#### Gradient
Let $f(x)$ be a feature extractor for $x$ (it returns a [[vector]] representation of $x$).
$$
\frac{\partial}{\partial w} loss(x^{(i)}, y^{(i)}, w)
$$
$$
\rightarrow \frac{\partial}{\partial w} \left[-w f(x) + log(1 + e^{w^Tf(x)}\right]
$$
$$
= -f(x) + \frac{1}{1 + e^{w^Tf(x)}}e^{w^Tf(x)}f(x)
$$
$$
= f(x)\left[-1 + \frac{e^{w^Tf(x)}}{1 + e^{w^Tf(x)}}\right]
$$
$$
= f(x)\left[P(y = 1\:|\:x)- 1\right]
$$
Note: $P(y|x)$ is what the *model* assigns to class $y$.
#### Updating w
$$
w = w + \alpha f(x)(1 - P(y = 1\:|\:x))
$$

---
# References
