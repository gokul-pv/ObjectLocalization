
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

Objective:
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



**GradCam on MisClassified Images**


# Analyzing COCO data format


  
## Coco Dataset:

We will be using a sample subset of data [link](https://github.com/gokul-pv/EVA6_Assignments_Session10/blob/main/PartB/sample_coco.txt)

The data format for bounding box is

- COCO Bounding box: (x-top left, y-top left, width, height) 

An example is
    id: 0, height: 330, width: 1093, bbox:[69, 464, 312, 175],

    id     - Image Id
    height - Image Original Height
    width  - Image Original Width
    bbox   - Bounding Box in COCO format (x-top left, y-top left, width, height)
