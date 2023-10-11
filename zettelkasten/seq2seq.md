202310101825

Tags: #nlp

# seq2seq
An Encoder-Decoder model that is good at handling inputs of arbitrary lengths.

It generates the next word conditioned on the previous output as well as input.

Similar to [[Language Model]]s except seq2seq deals with mapping one sequence to another (input to output) compared to Language Models that predict the next element/word.  

$$
P(y_i | x, y_1,\dots,y_{i-1}) = softmax(Wh)
$$
$$
P(y|x) = \prod_{i=1}^n P(y_i|x, y_1,\dots,y_{i-1})
$$
The size of $W$ is $|vocab|\times|hidden\:state|$
#### Use Cases
- Machine Translation
- Text summarization
- Chatbots
#### Inference
The argmax over word predictions is computed and fed into the next [[Transformer]] call.  Decoder is advanced one state at a time until `[STOP]` is reached.
#### Training
Maximize the probability of the gold sequence $y$ (now conditioned on the input $x$).

#### Architecture
The Encoder and Decoder could use [[RNN]], [[LSTM]], or [[Transformer]]s.
##### Encoder
Responsible for processing the input sequence which is captured in a fixed-length context vector.
##### Decoder
Takes the context vector from the encoder and generates an output sequence (one word/element at a time).  It can be [[Autoregressive]] to continue the sequence, or it can be a [[FFN]].

---
# References
https://www.youtube.com/watch?v=TKZkvqb-qpM
