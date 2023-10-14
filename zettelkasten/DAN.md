202310102236

Tags: #nlp

# DAN
Deep Averaging Network.

A [[Neural Network]] that is used for semantic classification problems in [[NLP]].

Variable-length input vectors are transformed into a fixed-length feature vector.

They're not great at capturing long-range contexts; they capture local patterns better than wider ones.

![[Pasted image 20231014105817.png]]

#### Parameters
$O(Vd + dh)$

where:
$V$ = number of words
$d$ = word embedding length
$h$ = hidden layer size

---
# References
https://www.youtube.com/watch?v=3pwwdHuH0I4