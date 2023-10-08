202210230623

Tags: #deeplearning

# Mask RCNN
Similar to [[Faster RCNN]] except there is a [[Semantic Segmentation]] mask at the end of the network.  

[[ROIPooling]] is replaced with ROI align since ROI Pooling snaps to the activation map too much.  [[Max Pooling]] is then used.

Good for [[Pose Estimation]] and [[3D Reconstruction]].

---
# References
