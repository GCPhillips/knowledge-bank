202310081726

Tags: #reinforcementlearning #nlp 

# Markov Property

An assumption where the current event/observation is conditionally independent of all previous events given the most recent one (or, a limited history of events/observations).

"The future is independent of the past given the present state that we're in."


##### Assumptions:
This is not always true:
$$
P(s'_t\ |\ s_{t-1},\ a_{t-1},\ \dots,\ s_0, a_0)\ =\ P(s'_t\ |\ s_{t-1}, a_{t-1})
$$

The state being observed contains the history of everything that happened before that.  This is not always true though.

---
# References
