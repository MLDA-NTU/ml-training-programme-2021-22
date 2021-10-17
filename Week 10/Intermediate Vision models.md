# Intermediate Vision models

## Object detection with YOLOv5

A "direct upgrade" to image classification is object detection. Compared to image classification, object detection aims to **localize** the detection i.e. find where in the image the object is.

Some popular models

- Faster R-CNN (good to read about the R-CNN family [here](https://lilianweng.github.io/lil-log/2017/12/31/object-recognition-for-dummies-part-3.html))
- YOLO family: YOLOv5, YOLOR, YOLOX (there are many more variants!)

## Deep dive into CNN architecture

Generally, most CNNs contain 5 stages. Each stage downsamples the image by 2 times and increases the number of channels.

E.g. ResNet-50, with input image 224 x 224 x 3

Stage | Input dimension | Output dimension
------|-----------------|-----------------
1 | 224 x 224 x 3 | 112 x 112 x 64
2 | 112 x 112 x 64 | 56 x 56 x 256
3 | 56 x 56 x 256 | 28 x 28 x 512
4 | 28 x 28 x 512 | 14 x 14 x 1024
5 | 14 x 14 x 1024 | 7 x 7 x 2048

Each stage **compresses the spatial dimensions** (h and w) while **expands the depth** (c). Thus sometimes people will say feature maps (intermediate outputs of convolution) at deeper layers (or stages) have weaker space information (reduced image resolution) but stronger semantic information (increased depth).

Some reasons for reducing image size

- Reduce computation
- Increase **receptive field**

Apart from the first convolution layer, all subsequent stages contain **less information**. For ResNet-50 model above, height and width is reduced by 2, and channel increases by 2, thus total information is halved after each stage.

For this reason, we can view CNNs as **Encoders**: compress information in an image by throwing away unimportant information, while still keeping necessary information for a given task.
