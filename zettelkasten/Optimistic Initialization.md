202312050701

Tags: #reinforcementlearning 

# Optimistic Initialization
A form of [[Optimism]].

To inifialize [[Expectation]]s of the [[Multi-Armed Bandit]] problem, knowing an upper bound is required.

The higher the initial value, the more you are likely to pull the arm until its expectation goes down.

This can be an issue when there are a large amount of actions; in this case, exploration would be very heavy and very little exploitation would occur.  However, in smaller action spaces this would drive exploration early on but eventually bring expectations down for exploitation.

---
# References
