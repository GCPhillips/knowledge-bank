202210112113

Tags: #deeplearning

# Focal Loss
Focal Loss is a [[Loss Function]] that is used in [[Object Detection]].  It cuts down the log likelihood loss when there are multiple negative influences, such as many regions in an image that are the 'not' of an object (such as 'this region is not a clock').

The formula is:
$$
-(1-p(y))^\gamma log p(y)
$$
The gamma ($\gamma$) is the amount of negative examples.  As it increases, the log likelihood loss flattens down more.

---
# References
