202312071404

Tags: #reinforcementlearning 

# Policy Improvement
The process of choosing a better [[Action]].

$$
\forall\ s, q_{\pi}(s, \pi'(s)) \geq v_{\pi}(s) \implies \forall\ s, v_{\pi'}(s) \geq v_{pi}(s)
$$
meaning, for every state $s$, if there is a policy $\pi'$ that is greater than or equal to the policy $\pi$, then it is an improvement on policy $\pi$.


---
# References
