202310092058

Tags: #nlp

# Probabilistic Context-Free Grammar
An extension of [[Context-Free Grammar]].  Probabilities are applied to the rules of the grammar.

For example:
```
S -> NP VP [1.0]
NP -> Det N [0.5]
VP -> V NP [0.5]
Det -> "The" [1.0]
N -> "cat" [1.0]
V -> "chased" [1.0]
```


---
# References
