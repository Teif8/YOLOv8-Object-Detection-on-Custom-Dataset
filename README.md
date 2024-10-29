# YOLOv8-Object-Detection-on-Custom-Dataset
This project provides a step-by-step guide to training a YOLOv8 object detection model on a custom dataset 

## Requirements

Python 3.8+
- Pip for package management
- GPU (optional but recommended): Ensure your environment (e.g., Google Colab) is set to use GPU for faster training. To enable it in Colab:
- Go to Edit > Notebook Settings > Hardware Accelerator > Select GPU.

 ## Installation

1. Clone Repository (optional): You may need to pull this notebook if not provided.
2. Install YOLOv8:
The recommended way to install YOLOv8 is through pip.
```
pip install ultralytics==8.2.103
``` 
3. Import Packages:
Import ultralytics and other necessary packages in the notebook.


## Training the Model

Initialize Model: 
Use YOLO("yolov8n.yaml") to define the model architecture and configuration.
Model Training Command:
Example command to initiate training:
```
!yolo task=detect mode=train model=yolov8n.yaml data=data.yaml epochs=50 imgsz=640
```

## Validating the Model

After training, validate the model on the validation set to assess its performance.
```
!yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=data.yaml
```
## Running Inference

To evaluate your custom-trained model on new images or a test dataset:
```
!yolo task=detect mode=predict model=runs/detect/train/weights/best.pt source='path/to/test/images'
```

## Results and Evaluation

During training, model performance metrics, such as loss curves, accuracy, and mAP, are logged.
You can visualize the results using plots and by comparing predicted outputs on test images.

## Resources

- Ultralytics YOLO Documentation
- Roboflow Universe


