202310081312

Tags: #nlp

# Hidden Markov Model

A [[Generative]] sequence model.  Used for generating a sequence for a [[Sentence]] or generating a sequence of [[Part-of-Speech]] [[Tag]]s.

The [[Part-of-Speech]] [[Tag]]s give syntactic structure of the [[Sentence]].

Pre-processing can be done with [[Smoothing]] and normalizing.

HMMs make a Markov assumption that only the current state drives the next step (and not the previous state(s)).  This is a little too aggressive especially since [[Context]] is needed to help drive predictions/generation.  To counteract this and add more context, pairs of [[Tag]]s can be used instead of single labeling of words.

##### Parameters
###### Initial Distribution / Start Probabilities
$P(y_1)$ is a $|\uptau|$ length column [[vector]].  It maps the probability of a [[Tag]] starting the sentence.
###### Transitions
A [[Transition Matrix]].  $P(y_i | y_{i-1})$ is a $|\uptau| \times |\uptau|$ [[matrix]].  It maps the probability of a [[Tag]] transitioning to another [[Tag]].
###### Emissions
An [[Emission Matrix]].  $P(x_i | y_i)$ is a $|\uptau| \times |V|$ [[matrix]].  It maps the probability of a word in a [[Sentence]] belonging to a specific [[Tag]] (i.e. "the probability of seeing a specific word given the [[Tag]]")

##### Object Types
###### Tag Set
$y_i \in \uptau_{tags}$
###### Words
$x_i \in V_{vocab}$

##### Formula
$P(\tilde{y},\tilde{x}) = P(y_1)\:P(x_1|y_1)\:P(y_2|y_1)\:P(x_2|y_2)\dots P(STOP|y_n)$

The $y$ values form a [[Markov Process]] ($y_i$ is conditionally independent of $y_1 - y_{i-2}$ given $y_{i - 1}$); it isn't completely independent of previous states.

##### Parameter Estimation
The goal is to maximize $\Sigma_i\:log\:P(\tilde{y}^{(i)}, \tilde{x}^{(i)})$, which is a generative [[joint distribution]].


---
# References
