# LSNet: A Unified Framework for Location-Sensitive Visual Recognition

<div align=center>
<img src=https://github.com/Duankaiwen/LSNet/blob/main/code/resources/lsvr.png width = "600" height = "250" alt="" align=center />
  
*The location-sensitive visual recognition tasks, including object detection, instance segmentation, and human pose estimation, can be formulated into localizing an anchor point (in red) and a set of landmarks (in green). Our work aims to offer a unified framework for these tasks.*
</div>

## Abstract

  Object detection, instance segmentation, and pose estimation are popular visual recognition tasks which require localizing the object by internal or boundary landmarks. This paper summarizes these tasks as location-sensitive visual recognition and proposes a unified solution named location-sensitive network (LSNet). Based on a deep neural network as the backbone, LSNet predicts an anchor point and a set of landmarks which together define the shape of the target object. The key to optimizing the LSNet lies in the ability of fitting various scales, for which we design a novel loss function named cross-IOU loss that computes the cross-IOU of each anchor-landmark pair to approximate the global IOU between the prediction and groundtruth. The flexibly located and accurately predicted landmarks also enable LSNet to incorporate richer contextual information for visual recognition. Evaluated on the MSCOCO dataset, LSNet set the new state-of-the-art accuracy for anchor-free object detection (a 53.5% box AP) and instance segmentation (a 40.2% mask AP), and shows promising performance in detecting multi-scale human poses. 

## Preparation
The master branch works with PyTorch 1.5.0

The dataset directory should be like this:
```plain
├── data
│   ├── coco
│   │   ├── annotations
│   │   ├── images
            ├── train2017
            ├── val2017
            ├── test2017
```

Generate extreme point annotation from segmentation:
- ```cd code/tools```
- ```python gen_coco_lsvr.py```
- ```cd ..```

## Installation

##### 1. Installing cocoapi 
- ```cd cocoapi/pycocotools```
- ```python setup.py develop```
- ```cd ../..```

##### 2. Installing mmcv 
- ```cd mmcv```
- ```pip install -e.```
- ```cd ..```

##### 3. Installing mmdet 
- ```python setup.py develop```

## Training and Evaluation
Our LSNet is based on [mmdetection](https://github.com/open-mmlab/mmdetection). Please check [with existing dataset](https://github.com/open-mmlab/mmdetection/blob/master/docs/1_exist_data_model.md) for Training and Evaluation.





