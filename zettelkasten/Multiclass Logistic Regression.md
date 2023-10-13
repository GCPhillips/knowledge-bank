202310112222

Tags: #machinelearning 

# Multiclass Logistic Regression
A [[Classification]] model where multiple classes are predicted.  For example, the probability of a picture containing a dog and/or cat.  It is similar to [[Logistic Regression]] except that it is multiple classes instead of binary.

#### Methods
Either:
###### One weight vector per class in the output (different weights)
(this option is typically what is seen)
$$
argmax_{y\:\in\:Y}\:w_y^Tf(x)
$$
###### Different features per class in the output
$$
argmax_{y\:\in\:Y}\:w^Tf(x, y)
$$
#### Loss
The Negative Log-Likelihood is:
$$
\frac{\partial}{\partial w}\:loss(x^{(i)}, y^{(i)}, w) = -f(x, y^{(i)}) + \sum_{y^{'}\:\in\:y}P(y^{'}|x)f(x, y^{'})
$$
Note: $P(y|x^{(i)})$ is what the *model* assigns to class $y$.
#### Update
In [[Stochastic Gradient Descent]], $w$ is updated with:
$$
-\alpha \times \frac{\partial}{\partial w}loss
$$

---
# References
