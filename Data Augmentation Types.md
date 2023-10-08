# Data augmentation techniques in computer vision
Cropping.
Flipping.
Rotation.
Translation.
Brightness.
Contrast.
Color Augmentation.
Saturation.

# Adding noise
For blurry images, adding noise on the image can be useful. By “salt and pepper noise”, the image looks like consisting of white and black dots.

Adding noise to images as a data augmentation technique.
soruce: medıum
Cropping
A section of the image is selected, cropped and then resized to the original image size. 

Cropping images as a data augmentation technique.
Source: Github
Flipping
The image is flipped horizontally and vertically. Flipping rearranges the pixels while protecting the features of the image. Vertical flipping is not meaningful for some photos, but it can be useful in cosmology or for microscopic photos.

Original image of a dog smiling.
Horizontal flip of an image containing a dog smiling.
Vertical flip of an image containing a dog smiling.
Source: MEDIUM, 1:ORIGINAL IMAGE – 2. HORIZONTAL FLIP – 3.VERTICAL FLIP
Rotation
The image is rotated by a degree between 0 and 360 degree. Every rotated image will be unique in the model.

Rotating images as a data augmentation technique.
Source: Medium
Scaling
The image is scaled outward and inward. An object in new image can be smaller or bigger than in the original image by scaling.

Scaling an image outward and inward as a data augmentation technique.
Source: Medium
Translation
The image is shifted into various areas along the x-axis or y-axis, so neural network looks everywhere in the image to capture it.

Shifting images on areas along x-axis and y-axis as a data augmentation technique.
Source:KDnuggets
Brightness
The brightness of the image is changed and new image will be darker or lighter. This technique allows the model to recognize image in different lighting levels.

Changing the brightness of images as a data augmentation technique.
Source: Tensorflow.org
Contrast
The contrast of the image is changed and new image will be different from luminance and colour aspects. The following image’s contrast is changed randomly.

Changing the contrast of images as a data augmentation technique.
Source: Tensorflow.org
Color Augmentation
The color of image is changed by new pixel values. There is an example image which is grayscale.

Changing the colors of images with new pixel values as a data augmentation technique.
Source: Tensorflow.org
Saturation
Saturation is depth or intensity of color in an image. The following image is saturated with data augmentation method.
