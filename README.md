# YOLO‑v3 Object Detection (TensorFlow Implementation)

This repository is an implementation of **YOLO‑v3** (You Only Look Once, version 3) for object detection, built in **TensorFlow**.

---

## Overview

YOLO‑v3 is a real-time object detection system that frames detection as a single regression problem, enabling extremely fast detection with good accuracy. This repository provides a TensorFlow-based implementation supporting both image and video inference.

---

## Features

- Load pre-trained YOLO‑v3 weights (COCO dataset)
- Perform inference on images and videos
- Adjustable Intersection over Union (IoU) and confidence thresholds
- Save detection results (images/videos)
- Utility scripts for weight conversion and handling detection output

---

## Project Structure

```
.
├── data/
│   ├── images/
│   └── video/
├── detections/            # Output folder for detection results
├── weights/               # Folder to store downloaded or converted weights
├── detect.py              # Main inference script
├── load_weights.py        # Script to convert Darknet weights to TensorFlow
├── yolo_v3.py             # Core YOLO‑v3 model definition
├── utils.py               # Utility functions (pre/post processing, drawing, etc.)
├── requirements.txt       # Python dependencies
└── README.md              # This file
```

---

## Requirements

- Python 3.6+
- TensorFlow
- NumPy
- Pillow
- OpenCV
- Seaborn

Install dependencies using the following command:

```bash
pip install -r requirements.txt
```

---

## Usage

### Converting Weights

Download the official Darknet YOLO‑v3 weights (trained on COCO):

```bash
curl -L -o weights/yolov3.weights https://pjreddie.com/media/files/yolov3.weights
```

Convert them to TensorFlow format:

```bash
python load_weights.py
```

### Running Detection

Run inference on images or video:

```bash
python detect.py <mode> <iou_threshold> <confidence_threshold> <input_paths...>
```

Example for images:

```bash
python detect.py images 0.5 0.5 data/images/road.jpg
```

Example for video:

```bash
python detect.py video 0.5 0.5 data/video/munich.mp4
```

Detected outputs are saved in the `detections/` folder.

---

## Examples

- Bounding boxes drawn over detected objects
- Works with both image and video inputs


![detection_1](https://github.com/user-attachments/assets/2e4e9300-8a31-4964-8217-00fe2f12ac6c)

![detection_2](https://github.com/user-attachments/assets/cc5440d6-19d9-46dd-b724-a67b44b824e9)


---
