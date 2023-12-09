202312091522

Tags: #reinforcementlearning 

# TD(lambda)
A form of [[Temporal Difference Methods]].

Works for both [[Episode]] and [[Continuing]] tasks.

In the continuing case and with TD(lambda), technically the full lambda-return cannot be computed exactly.


### True Online Variant
True Online TD(lambda) is a variant where:

- it is "truer" to the forward view of [[Lambda Return]]s
- The [[Eligibility Trace]] used in True Online TD(lambda) is called "[[Dutch Trace]]"
- It uses less memory than Offline (not "conventional") implementation of [[Lambda Return]]s would
- It can be expected to perform better than Offline

---
# References
