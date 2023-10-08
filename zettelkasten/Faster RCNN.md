202210101931

Tags: #deeplearning

# Faster RCNN
Faster RCNN is an [[Object Detection]] network and an improvement on [[RCNN]].  It addresses two issues with RCNN: slow speed (around 1 second per image) and how it relies too much on region proposals.

### Speed Improvements
Faster RCNN runs around 200 ms per image.  To achieve this speed improvement, the entire image is fed through all [[CNN]] layers.  The activation map will then contain interesting regions.  To crop and correlate the region bounds between the activation map and the image, [[ROIPooling]] is used.

### Region Improvements
Region detection is no longer a lower-level algorithm.  The same [[CNN]] is used to find interesting regions and to classify them.




---
# References
