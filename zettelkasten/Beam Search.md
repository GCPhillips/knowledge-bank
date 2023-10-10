202310092127

Tags: #nlp 

# Beam Search
Used frequently in [[seq2seq]] conditional generation settings like [[Machine Translation]] where finding the highest-probability hypothesis is really important.

Instead of performing an [[Exhaustive Search]], it is instead approximated by keeping the top k hypotheses at each step.

![[Pasted image 20231009213003.png]]

##### Issues
- the model is locally contextualized
- loops over words can happen
- the contexts are likely, but not the sequence
---
# References
https://www.youtube.com/watch?v=wltqDbhlcJ0