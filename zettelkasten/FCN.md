202210191920

Tags: #deeplearning

# FCN

"Fully Convolutional Network", FCN is how to achieve [[Semantic Segmentation]].  It has two phases:

### Encoding
The tensor goes through a network of convolutions and [[Max Pooling]] to decrease the size of the image but increase the channels (features).  This is so the number of parameters are reduced (to save compute resources, time and space) but the "important" features of the image are maintained.

### Decoding
Since the spatial dimensions of the image are reduced, a network of convolutions and transposition convolutions are used to increase the spatial dimensions (resolution) of the image.  This way, the feature map which detects the objects can then be used as a mask over the original image for a pixel-by-pixel mapping.

![[Pasted image 20221019192838.png]]

---
# References
[Towards Data Science](https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47)