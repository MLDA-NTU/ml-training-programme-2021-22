# Intermediate Vision models

## Object detection with YOLOv5

A "direct upgrade" to image classification is object detection. Compared to image classification, object detection aims to **localize** the detection i.e. find where in the image the object is.

Some popular models

- Faster R-CNN (good to read about the R-CNN family [here](https://lilianweng.github.io/lil-log/2017/12/31/object-recognition-for-dummies-part-3.html))
- YOLO family: YOLOv5, YOLOR, YOLOX (there are many more variants!)

**General steps for a typical Application-based Machine Learning project**

0. Translate application task into a specific machine learning task
1. **Construct dataset**
2. Choose a model
3. Train the model
4. Evaluate and visualize results
5. Hyper-parameters tuning
6. Deploy ML model to the application

Easy-to-use frameworks will handle steps 3-5 for you. Your main work will be on step 1, constructing the dataset.

Usually each Object detection framework will use a specific dataset format. Some pouplar formats are COCO, Pascal VOC, and YOLO. You also need to make sure that your data is converted correctly to the supported formats by your chosen framework. If you use a data labelling tool, like [CVAT](https://github.com/openvinotoolkit/cvat) or [Roboflow](https://roboflow.com/), they will handle data format conversion for you, so you can focus on labelling the data.

For step 2, you can take a look at the best performing models (SOTA) for a well-established dataset for that task, such as COCO 2017 for Object Detection. Example: https://paperswithcode.com/sota/object-detection-on-coco

However, the benchmark does not consider:

- Speed. For many applications, model speed is an important metric
- Ease of use. Research code for SOTA models is usually not simple to train on a custom dataset, and not well structured to adapt for your own projects.

Some frameworks that are easy to use:

- YOLOv5: https://github.com/ultralytics/yolov5
- Detectron2: https://github.com/facebookresearch/detectron2
- mmdetection: https://github.com/open-mmlab/mmdetection
- YOLOX: https://github.com/Megvii-BaseDetection/YOLOX
- TensorFlow Object Detection API: https://github.com/tensorflow/models/tree/master/research/object_detection

Generally there are 2 ways to build an ML application:

- Use a pretrained model and don't train it. Objects of interest must be present in the pre-trained dataset. COCO dataset has a lot of objects. Chances are, your objects of interest are included in COCO classes.
- Train on your custom data. Do this when the performance from using the first option is bad, or your objects of interest are not in the pre-trained dataset.

## Deep dive into CNN architecture

Generally, most CNNs contain 5 stages. Each stage downsamples the image by 2 times and increases the number of channels.

E.g. ResNet-50, with input image 224 x 224 x 3 (See Table 1 in the ResNet paper. [[PDF](https://arxiv.org/pdf/1512.03385.pdf)])

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

## Semantic segmentation

Semantic segmentation can be seen as a **pixel-wise classification**: we want to classify each pixel to some pre-defined classes. If you want to read more about Semantic segmentation: https://nanonets.com/blog/semantic-image-segmentation-2020/

**Architecture** A simple architecture for Semantic segmentation will be a **Fully convolutional network** (FCN). On top of the CNN Encoder (that is taken from an Image classifier), we add a few **upsample** stages, usually 3. For each stage, we will have a layer that performs upsampling (either convolution transpose or image interpolation) and a convolution layer to "refine" the upsampled feature map. This is also called a **Decoder**: interpret the encoded information to make a prediction.

For Image classification, we don't need spatial information. **Where** the object is in the image is not important, we only need to know **whether** the object is in the image. Thus, the encoder structure of typical CNN classifiers (that throw away spatial information) is fine.

However, for object detection and segmentation, spatial information is particularly important because we need **localization**: predict where the object is in the image. There are generally two approaches to this problem:

- Design CNNs specifically for object detection (or segmentation)
- Use tricks to adapt CNN classifiers for object detection (and segmentation)

Most innovations in CNN architectures start with Image classification. It is a shame if we can't leverage those innovations from Classification in the domain of Detection and Segmentation. In facts, many Object detectors are **meta-architecture**: they can be adapted to use with any backbones, which are usuallly CNN Classifiers.

Some backbones designed for Object detection / segmentation: DarkNet-53, MobileDet

Some tricks to adapt CNN classifiers (sometimes called **neck** and **feature fusion**): Feature Pyramid Network (FPN), U-Net, Deep Layer Aggregation (DLA)


