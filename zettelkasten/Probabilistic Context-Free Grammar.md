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

They are built by estimating a grammar from a [[Treebank]] and then parsing with that grammar.  The issue with this is that it will build a bad parser since the [[Context-Free Grammar]] is too context-free.  Refinement is needed to make it better (such as with [[Markovization]], [[Lexicalization]], etc.).

For example:
![[Pasted image 20231014092629.png]]

As seen above, the rewrite rule for **NP** for all **NPs** is **NP $\rightarrow$ NP PP** at 11%.
However, if it is under **S**, 21% it will be **PRP**.  Obviously from this example, language is not context-free.

Different techniques exist to make the PCFG stronger, such as [[Vertical Markovization]].

---
# References
https://www.youtube.com/watch?v=f1o1_bPWzM0