202210142233

Tags: #deeplearning

# Pooling
Used in [[CNN]] to help generalize an activation regardless of orientation from the network.  For example, if the network is trained to detect the number '9', if there are many convolutional filters that detect different rotations of the number and one activates, pooling will help activate even though only one filter is heavily activated.  In this case, it would be [[Max Pooling]].

![[Pasted image 20221014223631.png]]

---
# References
[Adventures in Machine Learning](https://adventuresinmachinelearning.com/convolutional-neural-networks-tutorial-in-pytorch/)