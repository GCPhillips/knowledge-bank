202210101937

Tags: #deeplearning 

# ROIPooling
ROIPooling is a layer in a deep [[CNN]] used to find the coordinates from an activation map and apply it to an image.  It takes two inputs:
1. The activation map from a [[CNN]]
2.  A matrix with a list of regions of interest (and their coordinates)

The important thing about ROIPooling is that it reuses the activation map from the network which means savings in time and compute resources.


---
# References
[deepsense.ai](https://deepsense.ai/region-of-interest-pooling-explained/)