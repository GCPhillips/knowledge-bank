202404251713

Tags: #math 

# Bayes' Rule
Calculates the probability of an event given prior knowledge of conditions that could be related to the event.

$$
P(A|B) = \frac{P(B|A)P(A)}{P(B)}
$$

##### Example

Given two coins, A and B, assume the probabilities of flipping heads and tails are:

| Coin | Heads | Tails |
| ---- | ----- | ----- |
| A    | 0.75  | 0.25  |
| B    | 0.25  | 0.75  |
If you flipped 4 heads in a row and want to calculate the probability of the next being a heads:
$$
\begin{flalign}
P(\{H\}|\{H, H, H, H\}) &= \frac{P(H, H, H, H, H)}{P(H, H, H, H)} \\
&= \frac{P(H^5| \text{coin}=A)\cdot P(\text{coin}=A) + P(H^5 | \text{coin}=B)\cdot P(\text{coin}=B)}{P(H^4| \text{coin}=A)\cdot P(\text{coin}=A) + P(H^4 | \text{coin}=B)\cdot P(\text{coin}=B)} \\
&= \frac{.75^5 \cdot \frac{1}{2} + .25^5 \cdot \frac{1}{2}}{.75^4 \cdot \frac{1}{2} + .25^4 \cdot \frac{1}{2}} \\
&\approx \frac{.1187 + .0005}{.1582 + .0019} \\
&\approx .7445
\end{flalign}
$$

---
# References
[Wikipedia](https://en.wikipedia.org/wiki/Bayes%27_theorem)