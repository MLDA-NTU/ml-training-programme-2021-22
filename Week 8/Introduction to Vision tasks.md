# Introduction to Vision tasks

Key takeaways: 

- (Theory) Why do we use Convolutional Neural Networks for Vision tasks?
- (Practical) How to use Transfer Learning for Image Classification

Resources

- Stanford CS231n (CNN): [link](https://cs231n.github.io/)

Other links

- Google Cloud Vision: https://cloud.google.com/vision
- Google Open Images: https://storage.googleapis.com/openimages/web/index.html
- Motional Nuscenes: https://www.nuscenes.org/
- This Person Does Not Exist: https://thispersondoesnotexist.com/
- Stanford CS236g (GAN): https://cs236g.stanford.edu/
- Torchvision models: https://pytorch.org/vision/stable/models.html
- MLDA Academics Recruitment task 2021: https://github.com/gau-nernst/mlda-acad-recruitment

Notebook used: Transfer Learning with PyTorch Lightning and Visualization of convolution filters (modified from the Recruitment task notebook)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MLDA-NTU/ml-training-programme-2021-22/blob/main/Week%208/Animal_crossing_vs_Doom.ipynb)

## Overview of vision tasks

Vision tasks does not only include **Images**, but also other data types such as **point cloud** and **video**. Some tasks we can do with vision:

- Image:
    - Basic: image classification, object detection (2D and 3D) and segmentation
    - Keypoints detection, landmark recognition, image generation, object tracking, monocular depth estimation
    - Pose estimation, re-identification (Face ID)
- Point cloud (3D): used in Autonomous Vehicles
    - Object reconstruction, object classifiction, object tracking
- Video: with temporal data
    - Video classification (action recognition), video detection and segmentation

## Image data

Normal images can be either monochrome with 1 color (grayscale) or colored with 3 channels (usually RGB). Colored photos can be encoded in other color spaces also. Special image data, such as **multispectral** satellite images, can have more than 3 channels.

After being decoded, an image is an array of pixels, usually in the shape of (height x width x channel).

## Convolution operation

Visualize convolution operation: https://setosa.io/ev/image-kernels/

CNN cheatsheet (all you need to know): https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-convolutional-neural-networks

- Filter / Kernel: the template patch being used to compare against. Usually 3x3 in CNNs. Note that filter is a 3D tensor with a depth/channel dimension
    - E.g. input image is 240x360x3. We can use a filter 5x5x3. For normal convolution, number of channels in the filter must match number of channels in the input image. Using 64 filters like that, we can produce an output image with 64 channels. Each channel in the output image corresponds to the result of a filter.
- Parameters:
    - Kernel size: size of the kernel e.g. 3x3
    - Stride: how much to move the kernel at each step. this determines the output resolution e.g. stride = 2 → output image is half the size of input image
    - Padding: add extra pixels at the edge to ensure output image has the same size as input image 
- Convolution properties
    - Translational equivariance
    - Weight sharing across spatial dimensions (can be used for temporal dimension too)
    - Local operation: convolution can't "see" pixels further away → concept of **receptive field** and stacking convolution layers to increase receptive field

## Advanced materials

- Other types of convolutions used in CNNs: 
    - depth-wise separable convolution (MobileNet, EfficientNet)
    - point-wise (1x1) convolution
    - group convolution
    - dilated (atrous) convolution (object detection and segmentation)
    - deformable convolution (object detection and segmentation)
- Notable CNN architectures
    - ResNet: skip connections to improve training stability for deep networks
    - MobileNet: use depth-wise separable convolution to reduce computations for mobile devices
- Compare convolution with transformer's attention
- Transformer-based models for vision tasks: ViT, DETR
