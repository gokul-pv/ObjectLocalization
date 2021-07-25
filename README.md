
# EVA6_Assignments_Session10
EVA6 Assignment for Session 10

# Object Localization
Object Localization is a very hard task to do because we should not only predict the object but also we need to detect the exact position of it.

### **Detection Approaches**

We can simplify Object Detection problem by:

1.  Ignoring lower prediction values
2.  Predicting bounding boxes instead of the exact object mask mixing different receptive field layers but this is easier said than done.

There are two main approaches to driving detection algorithms, namely:

1.  YOLO-like approach, where k-means extracted anchor boxes are used, and
2.  SSD-like approach, where a fixed number of predefined bounding boxes are used.

## Part A: [TinyImageNet](https://github.com/gokul-pv/EVA6_Assignments_Session10/tree/main/PartA)

**Objective**:
-   Download this  [TINY IMAGENET](http://cs231n.stanford.edu/tiny-imagenet-200.zip) dataset.
-   Train ResNet18 on this dataset (70/30 split) for 50 Epochs. Target 50%+ Validation Accuracy.

**Parameters**
1.  Augmentations - Horizontal flip, Padding , Random Crop, Cutout and Normalization
2.  Batch Size - 256
3.  Model - Resnet 18 with 200 classes
4.  Optimizer - SGD(momentum - 0.9 , weight_decay - 0.0001)
5.  Scheduler - One Cycle ( max_lr = 0.02, epochs=30, pct_start=1/3, anneal_strategy='linear', cycle_momentum=True, base_momentum=0.85, max_momentum=0.95, div_factor=10.0,final_div_factor =10)

**Results**

1.  Best train Accuracy - 77.83%
2.  Best test Accuracy - 57.55%

<p align="center" style="padding: 10px">
<img alt="Forwarding" src="https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/Images/log23-30.png?raw=true" width =500><br>
<em style="color: grey">Figure 1 : Training log</em>
 </p> 
 
<p align="center" style="padding: 10px">
<img alt="Forwarding" src="https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/Images/Accuracy.png?raw=true" width =500><br>
<em style="color: grey">Figure 2 : Accuracy plot</em>
 </p> 

**GradCam on MisClassified Images**

<p align="center" style="padding: 10px">
<img alt="Forwarding" src="https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/Images/GradCam.png?raw=true" width =500><br>
<em style="color: grey">Figure 3 : GradCam</em>
 </p> 


## Part B: Analyzing COCO data format


  
## Coco Dataset:

**Objective**
1.   Learn how COCO ([link](https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/PartB/sample_coco.txt)) object detection dataset's schema is . This file has the same schema. You'll need to discover what those number are.
2. Identify these things for this dataset:
    -  Class distribution (along with the class names) along with a graph
    -  Calculate the Anchor Boxes for k = 3, 4, 5, 6 and draw them.

**What is The COCO Dataset?**

COCO annotations are inspired by the [Common Objects in Context (COCO) dataset](http://cocodataset.org). 

> "COCO is a large-scale object detection, segmentation, and captioning dataset. COCO has several features: Object segmentation, Recognition in context, Superpixel stuff segmentation, 330K images (>200K labeled), 1.5 million object instances, 80 object categories, 91 stuff categories, 5 captions per image, 250,000 people with keypoints."

It is one of the best image datasets available, so it is widely used in cutting edge image recognition artificial intelligence research. It is used in open source projects such as 
- [Facebook Research's Detectron](https://github.com/facebookresearch/Detectron), 
- [Matterport's Mask R-CNN](https://github.com/matterport/Mask_RCNN), 
- [endernewton's Tensorflow Faster RCNN](https://github.com/endernewton/tf-faster-rcnn) 
- for Object Detection, and others.

**COCO Dataset Format**
The COCO dataset is formatted in JSON and is a collection of “info”, “licenses”, “images”, “annotations”, “categories” (in most cases), and “segment info”.

An example of data from ([link](https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/PartB/sample_coco.txt)) is shown below: 

>    id: 1, height: 782, width: 439, bbox:[359, 292, 83, 199]

    id     - Image Id
    height - Image Original Height
    width  - Image Original Width
    bbox   - Bounding Box in COCO format (x-top left, y-top left, width, height)

**Class Distribution**
There are 80 categories in the provided dataset and its distribution is shown below:

<p align="center" style="padding: 10px">
<img alt="Forwarding" src="https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/Images/ClassDistribution.png?raw=true" width =1000><br>
<em style="color: grey">Figure 4 : COCO class distribution </em>
 </p> 

