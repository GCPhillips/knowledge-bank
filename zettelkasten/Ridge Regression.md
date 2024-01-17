202401150705

Tags: #optimization #machinelearning 

# Ridge Regression
An optimization problem that can be solved via [[Gradient Descent]] or [[Newton's Method]].
Typically used when the columns are nearly co-linear.

$$
\text{minimize}: \frac{1}{n}||\ X\beta - y\ ||_2^2 + \lambda ||\ \beta\ ||_2^2
$$
which is equivalent to:
$$
\text{minimize}: \frac{1}{n} \sum_{i=1}^n (x_i^T\beta - y_i)^2 + \lambda \sum_{j=1}^d \beta_j^2
$$


---
# References
