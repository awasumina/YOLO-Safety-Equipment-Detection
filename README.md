# YOLO Safety Equipment Detection

This project aims to detect safety equipment such as helmets, gloves, jackets, goggles, and footwear in images using the YOLO object detection model.

## Project Overview

This repository contains the custom-trained YOLO model, which has been fine-tuned on a dataset of safety equipment images. The objective of this model is to detect safety gear in images to ensure compliance with safety protocols in various work environments.

### Key Features:
- **Object Detection**: Detects helmets, gloves, jackets, goggles, and footwear.
- **YOLO Model**: Trained using Ultralytics YOLOv8.
- **Custom Dataset**: Safety equipment dataset collected from real-world images.
- **Real-Time Detection**: Capable of detecting equipment in real-time.


## Training the Model

1. Clone the repository and navigate to the working directory:
   ```bash
   %cd /content/drive/MyDrive/yolo_v8_safety_equipment_detect
   ```

2. Train the model with the following command:
   ```bash
   !yolo task=detect mode=train model=yolov8s.pt data=data.yaml epochs=25 imgsz=265 plots=True
   ```

## Validation

After training, validate the model to check its performance:
```bash
!yolo task=detect mode=val model=runs/detect/train4/weights/best.pt data=data.yaml
```

## Inference

For inference on test images, run the following command:
```bash
!yolo task=detect mode=predict model=runs/detect/train4/weights/best.pt conf=0.25 source=data/test/images
```

## Results

Sample Results:

- Confusion Matrix:
  ![Confusion Matrix](https://github.com/awasumina/YOLO-Safety-Equipment-Detection/blob/main/results/confusion_matrix.png)

- Training Results:
  ![Training Results](https://github.com/awasumina/YOLO-Safety-Equipment-Detection/blob/main/results/results.png)

- Validation Example:
  ![Validation](https://github.com/awasumina/YOLO-Safety-Equipment-Detection/blob/main/results/results.pngval_batch0_pred.jpg)

## Model Performance

- **Precision**: Measures the accuracy of detecting safety equipment correctly.
- **Speed**: Optimized for real-time detection with fast inference times.
- **Efficiency**: Custom YOLOv8 model tuned for detecting multiple objects simultaneously.
