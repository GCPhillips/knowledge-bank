202310101345

Tags: #nlp 

# BERT
Bidirectional Encoder Representations from [[Transformer]]s.

Cannot generate text that well (it is in order of $n^2$).  

Uses both left and right [[Context]]s.

The same words are masked in each epoch.

Similar to [[BART]], except it is only an Encoder [[Transformer]].

It is a [[Masked Language Model]]:
- a chunk of text is taken, 15% of tokens are masked out which are attempted to be predicted
- it allows to look at everything but not cheat
- better at analysis than generation (which *is* possible, but it isn't really intuitive)

#### Use Cases
- Single sentence classification tasks
- Sentence pair classification tasks
	- [[Transformer]]s can capture interactions between two sentences (sentence 'a' implies sentence 'b', such as `[CLS] A boy plays in the snow [SEP] A boy is outside`)
- Single sentence tagging tasks

![[Pasted image 20231010135216.png]]

---
# References
https://www.youtube.com/watch?v=dya_QNFvtiQ
https://www.youtube.com/watch?v=g96oi4ihc_E
