202310102215

Tags: #nlp

# Attention
A mechanism for accessing info in the [[Context]] to be able to make predictions.

Allows to arbitrarily go far back in the [[Context]].

Allows for understanding of relationships between different parts of input data.

Used in [[Transformer]] architectures.

#### Parameters
Three vectors are learned during training process.  All three vectors are representations associated with each element in the input sequence.
##### Key
- Embeddings of the sequence
- The input sequence
- Used to determine the similarity or compatibility between the query and the elements in the sequence (higher score $\rightarrow$ more compatibility)
##### Query
- What we want to find / what we want to find [[Context]] for
- For example, in a [[Language Model]], it could be the representation of the current word you're trying to generate or the target word in [[Machine Translation]]
##### Value
- Represents the actual information or content of the elements
- Used to provide weighted contributions to the output based on the computed attention weights

---
# References
