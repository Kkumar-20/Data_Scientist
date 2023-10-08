# What is a feature map?
- Many candidates are rejected or down-leveled in technical interviews due to poor performance in behavioral or cultural fit interviews. Ace your interviews with this free course, where you will practice confidently tackling behavioral interview questions.

Get Free Course
In a convolutional neural network (CNN), feature maps are the output of the convolutional layer after the convolution operation has occurred on an image passed to the convolutional layer.

How are feature maps formed?

Convolution operation

Convolution operation
In the illustration above, we can see how feature maps are formed from a provided input image.

The image to be sent to the convolutional layer is a multi-dimensional array containing pixel values. The convolutional layer includes filters that are matrices that will be multiplied with the image, and the result will be a feature map(s).

If we have multiple filters, each filter is individually multiplied with the input image and returns a different feature map for each filter.

How to tune feature maps
To tune feature maps, we can use the three ways listed below.

Stride: This refers to the number of jumps we want the filter to move after each multiplication operation on the input image. A stride of N means N pixel jumps. A large stride value reduces the size of the feature map.

Depth: It refers to the number of filters we want to use for the convolution operation. Each filter gives an individual feature map. N filters will give N feature maps.

Padding: We can also provide padding to the original input image by appending additional pixels to the borders of the input image.

In the diagram below, we can see how these three methods work collectively to form feature maps.


Initial Layers

Initial Layers
1 of 5

Uses of feature maps
Feature maps are used in convolutional neural networks for several reasons, some of which are mentioned below.

Detect important features: Initially, the feature maps capture low-level patterns, but as they propagate to successive layers, they detect new patterns and combine them to form high-level features.

Feature sharing: A feature map is passed through multiple layers in a neural network for image processing; hence, the features found by the previous layers are propagated to each successive layer.

Object recognition: Feature maps can also be passed to an artificial neural network which can be trained to predict the object in the image.

Image segmentation: Feature maps can divide an image into different segments, each representing a meaningful part of the unsegmented image.
