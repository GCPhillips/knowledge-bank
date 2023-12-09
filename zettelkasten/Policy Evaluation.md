202312071404

Tags: #reinforcementlearning 

# Policy Evaluation
The process of seeing what the value of a state is given that the [[Policy]] is followed.

The policy is assumed to be known.

$$
v_k(s)
$$
is how much reward you could get from state $s$ if there are $k$ steps taken.  For example, $v_0(s)$ would return 0 (or whatever the initial value of the state is) since no actions would be taken.

Update method:

$$
v_{k+1}(s) = \sum_a\pi(a|s)\sum_{s', r}p(s', r| s, a)[r + \gamma v_k(s')]
$$

---
# References
