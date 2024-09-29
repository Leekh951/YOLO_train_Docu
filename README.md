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

   - **RT-DETR Model**:
     ```python
     model = RTDETR('rtdetr-resnet50.yaml')
     ```
     - This line loads the RT-DETR model based on a configuration file (`rtdetr-resnet50.yaml`).
     - The configuration file defines the model architecture (e.g., backbone, number of layers, etc.) and other settings.
     - You need to ensure
