202312041843

Tags: #reinforcementlearning 

# Epsilon-Greedy Exploration
At epsilon fraction of the time, a random action is taken.

$$
\epsilon = 0 \rightarrow \text{greedy exploration is always chosen}
$$
$$
\epsilon \gt 0 \rightarrow \text{random action has a probability of being chosen}
$$
In general, epsilon = 0 is not a great strategy since it means exploration never occurs.

##### Example
From homework 2.1:

In $\epsilon$-greedy action selection, for the case of two actions and $\epsilon = 0.5$, what is the probability that the [[Greedy Action]] is selected?

P(greedy) = P(select greedy) + P(random greedy)
P(greedy) = 0.5 + 0.5 * 0.5
P(greedy) = 0.75

---
# References
