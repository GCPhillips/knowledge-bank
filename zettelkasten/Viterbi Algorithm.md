202310081249

Tags: #nlp

# Viterbi Algorithm

An algorithm that uses [[Dynamic Programming]] to make an inference on [[Hidden Markov Model]].

##### Inference 
$argmax_\hat{y}\:P(\hat{y}|\hat{x})$
$= argmax_{\hat{y}}\:\frac{P(\hat{y}, \hat{x})}{P(\hat{x})}$

($P(\hat{x})$ is constant w.r.t. $\hat{y}$)

$= argmax_{\hat{y}}\:P(\hat{y}, \hat{x})$
$= argmax_{\hat{y}}\:log\:P(\hat{y}, \hat{x})$
$= argmax_{\tilde{y}_1\dots\tilde{y}_n}\:log\:{P(\tilde{y}_1)}\:+\:log\:P(x_1|\tilde{y}_1)\:+\:log\:P(\tilde{y}_2|\tilde{y}_1)\:+\:\dots$

![[Pasted image 20231008130737.png]]

##### Dynamic Programming
1.) Define
$v_i(\tilde{y}) = n \times |\uptau|$

$|\uptau|$ is the number of [[Tag]]s

2.) Base Case
$v_1 (\tilde{y}) = log\:P(x_1|\tilde{y}) + log\:P(\tilde{y})$

3.) Recurrent Case
$v_i(\tilde{y}) = log\:P(x_i|\tilde{y}) + max_{\tilde{y}_{previous}}\: log\:P(\tilde{y}|\tilde{y}_{previous}) + v_{i-1}(\tilde{y}_{previous})$

##### Algorithm
```
for i = 1...n:
	for j = 1...n:
		compute $v_i (\tilde{y})$
compute $v_{n+1}$ (STOP)
```


---
# References
https://www.youtube.com/watch?v=Ks7IrsjhqSo