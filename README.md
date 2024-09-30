# YOLO Training Script Documentation

## Overview

This document provides an explanation of how to use the `train.py` script for training object detection models, specifically YOLOv8 and RT-DETR models, using a custom dataset. The script is implemented in Python and uses the `ultralytics` library to load and train the models.

## Prerequisites

- Python 3.x
- `ultralytics` library (`YOLO` and `RTDETR` classes)
- `torch` library for PyTorch operations

You can install the required packages via pip:

```bash
pip install ultralytics torch
```


1. **Model Loading**:

   - **YOLO Model**:
     ```python
     model = YOLO('yolov8l.pt')
     ```
     - This line loads a pre-trained YOLOv8 model using the pre-trained weights file (`yolov8l.pt`).
     - You can use different versions of YOLO models (e.g., `yolov8s.pt`, `yolov8m.pt`, etc.) by specifying the corresponding `.pt` file.
     - The YOLO model file (`.pt`) typically contains the complete model architecture and pre-trained weights.
     - If you want to use a non pre-trained model, use a `.yaml` file
       
   - **RT-DETR Model**:
     ```python
     model = RTDETR('rtdetr-resnet50.yaml')
     ```
     - This line loads the RT-DETR model based on a configuration file (`rtdetr-resnet50.yaml`).
     - The configuration file defines the model architecture (e.g., backbone, number of layers, etc.) and other settings.
     



---

# How to Run `eval.py`

## Verify Python Installation
Make sure Python 3.x is installed. If it is not installed, you can download it from the official [Python website](https://www.python.org/downloads/).

## Install Required Libraries
Install the required libraries using the command below:

```bash
pip install numpy opencv-python
```

The packages `numpy` and `opencv-python` are necessary for tasks such as IoU calculation and coordinate transformation in the script.

## Run the Script
You can run the `eval.py` file by typing the following command in the terminal:

```bash
python eval.py
```

Ensure that the paths for `gt_folder` and `pred_folder` are correctly set within the script. These paths should point to the folders containing the ground truth data and prediction data, respectively.

## Modify Folder Paths and Image Size
Before running the script, you need to modify the following part of the `eval.py` file:

```python
gt_folder = '/path/to/groundtruths'  # Path to the folder containing ground truth data
pred_folder = '/path/to/predictions' # Path to the folder containing prediction data
image_width = 2048  # Width of the image
image_height = 1080 # Height of the image
```

- `gt_folder` and `pred_folder` should be set to the paths of the folders containing ground truth labels and predicted labels, respectively.
- `image_width` and `image_height` should match the actual size of the images in the dataset.

## Output Results
After running the script, it will output metrics such as `mAP@50` and `mAP@50-95`. These values are used to evaluate how accurately the model detects objects.

--- 

