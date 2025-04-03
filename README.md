# Autonomous Driving Application: Car Detection

This repository contains an implementation of a YOLO-based object detection system for identifying and localizing cars in images, tailored for autonomous driving applications.

## Features

- **YOLO Architecture**: Utilizes the YOLO (You Only Look Once) object detection model for real-time predictions.
- **Bounding Box Filtering**: Implements score thresholding and non-max suppression to refine detections.
- **Customizable Detection Parameters**: Allows adjustment of thresholds and maximum bounding boxes.
- **Visualization**: Draws and saves bounding boxes on the detected objects.

## Prerequisites

- Python 3.7+
- TensorFlow 2.0+
- Required Python libraries: `numpy`, `matplotlib`, `PIL`, `pandas`, `scipy`

Install the dependencies using:

```bash
pip install tensorflow numpy matplotlib pillow pandas scipy
```

## Usage

1. **Setup**:
   - Ensure the following files are present in the `model_data/` directory:
     - `coco_classes.txt`: Class labels for COCO dataset.
     - `yolo_anchors.txt`: YOLO anchor configurations.
     - YOLO model weights.
   - Place test images in the `images/` directory.

2. **Run the Script**:
   - Execute the `Autonomous_driving_application_Car_detection.py` script to detect objects in the test images.
   - Predictions will be saved in the `out/` directory with bounding boxes drawn on them.

3. **Configuration**:
   - Modify the following parameters in the script if necessary:
     - `max_boxes`: Maximum number of bounding boxes (default: 10).
     - `score_threshold`: Confidence threshold for box filtering (default: 0.6).
     - `iou_threshold`: Intersection-over-union threshold for non-max suppression (default: 0.5).

4. **Output**:
   - The script outputs detected bounding boxes, class scores, and class labels for each image.

## Key Functions

- **`yolo_filter_boxes`**: Filters boxes based on class confidence scores.
- **`iou`**: Computes the Intersection-over-Union (IoU) between two bounding boxes.
- **`yolo_non_max_suppression`**: Refines boxes using non-max suppression.
- **`predict`**: Performs object detection on a given image and visualizes the results.

## Example Results

Given an input image, the model detects cars and other objects, returning the bounding box coordinates, confidence scores, and class labels. The detected objects are highlighted in the output image.

## Model Summary

The YOLO model predicts bounding boxes and class probabilities in a single forward pass, making it suitable for real-time applications. This script integrates the YOLO outputs with additional processing for effective object detection.


