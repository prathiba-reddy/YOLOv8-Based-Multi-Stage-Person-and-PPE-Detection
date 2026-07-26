# YOLOv8-Based-Multi-Stage-Person-and-PPE-Detection
Implemented a multi-stage YOLOv8-based pipeline for person detection and PPE identification, with image cropping, inference, and OpenCV-based visualization.


This project implements a two-stage object detection pipeline using YOLOv8 to detect persons and their personal protective equipment (PPE) in images. The system first detects persons, crops their images, and then performs PPE detection on each cropped person. The results are then mapped back onto the original image for visualization using OpenCV.

Project Workflow

**Train YOLOv8 for Person Detection**
Used YOLOv8 to train a model that detects persons in images.
Generated bounding boxes for each detected person.

**Train YOLOv8 for PPE Detection**
Trained another YOLOv8 model to detect PPE items (hard-hat, gloves, mask, glasses, boots, vest, PPE-suit, ear protector, safety harness) on cropped person images.

**Data Preprocessing**
Developed a logic to transform full-image PPE annotations to cropped person images.
If an image contained multiple persons, it was split into separate images, each containing a single person.
Inference Pipeline (Person_PPE detection.py) and The person_detection.py is for only person detection .
Takes an input directory containing images.
Runs the person detection model to get bounding boxes.
Crops each detected person and applies the PPE detection model.
Maps PPE detections back to the original full image.

**Visualization with OpenCV**
Used OpenCV’s cv2.rectangle() and cv2.putText() to draw bounding boxes and confidence scores.
Avoided YOLO’s built-in drawing functions to maintain customization and flexibility.
