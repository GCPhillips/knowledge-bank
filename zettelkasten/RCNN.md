202210101837

Tags: #deeplearning 

# RCNN
RCNN is one of the first [[Object Detection]] networks.  Since [[CNN]] works well with image classificiation, RCNN tries to use it for detecting object(s) within an image.

### Issues and Solutions
1. **Issue**: There could be a huge amount of possible potential regions.  For example, in a 500x500 image, there could be $(500^2)^2$ possible regions.  
 
   **Solution**: Use a low-level algorithm that detects potential regions within the image based on interesting features.
   
2. **Issue**: There could be multiple regions around a single object.  For example, if there is a chair in the image, there could be 5 regions around it although it's for the same object.
 
   **Solution**: Use [[Non-Maxima Suppression]] to filter out detections close to a strong detection

3. **Issue**: Region proposals might not bound around the whole object, such as not including the legs of a chair.
 
   **Solution**: Use [[Bounding Box Regression]] to find precise location of the object.


### Algorithm

- Make proposals on regions for objects within the image.  The regions are highlighted based on "interesting" features (such as edges, etc.).  The regions are class-agnostic so no labels are created.
- Crop and resize all regions
- For each region to classify:
	- See if it is an object
	- Regress to get the actual location of the object
- Extract detections using [[Non-Maxima Suppression]]


### Drawbacks
- The algorithm is very slow (1 minute per image)
- It relies too much on the region proposal mechanism



---
# References
