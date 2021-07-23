# EVA6_Assignments_Session10
EVA6 Assignment for Session 10


# Object Localization

## [TinyImageNet](https://github.com/gokul-pv/EVA6_Assignments_Session10/tree/main/PartA)

Objective:
-   Download this  [TINY IMAGENET](http://cs231n.stanford.edu/tiny-imagenet-200.zip) dataset.
-   Train ResNet18 on this dataset (70/30 split) for 50 Epochs. Target 50%+ Validation Accuracy.



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
