202310101903

Tags: #nlp

# BART
Bidirectional and Auto-Regressive [[Transformer]]s.

A pre-training technique for [[seq2seq]] ($P(y|x)$).

Similar to [[BERT]] for generating a sequence except for the addition of an [[Autoregressive]] Decoder for generating text (rather than analysis).

#### Use Cases
- Good for generating summaries of input texts
#### Pre-training
Take random chunks of text, add noise to them, try to decode the clean text.

---
# References
