202210112053

Tags: #deeplearning 

# RetinaNet
RetinaNet is an [[Object Detection]] network and a placeholder for [[Single Stage Detector]].  Instead of having the Region Proposal Network (RPN) split off from the activation map along with the [[ROIPooling]] on a separate branch, the [[ROIPooling]] is instead removed.  This allows the network to be able to be trained end-to-end.

The activation map also classifies the regions.

RetinaNet is faster than [[Faster RCNN]].

### Issues and Solutions
1. **Issue**: What if an image classifies a region correctly with an object, such as a clock, but also has hundreds of regions that are classified as 'not a clock'?  This will train the model to learn 'not a clock' due to the huge influence on negative gradients (from the loss function). 
 
   **Solution**: Use [[Focal Loss]] function, which will cut down the log likelihood loss.


![[Pasted image 20221011205615.png]]




---
# References
