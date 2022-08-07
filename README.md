# Object-Detection-For-Autonomous-Vehicle-Jetson-Nano-
This is my project for Deep Learning in Intelligent Video Analytics and Computer Vision Workshop in IIUM.

This project is an object detection for autonomous vehicles using the Yolov5 deployed at the Jetson Nano. The framework is the Pytorch and is run on Google Colab.  

#Hardware requirement:
1. Jetson Nano 2GB
2. 5V DC Barrel jack (or Micro-USB power supply)
3. MicroSD card (32GB UHS-1 minimum recommended)
4. Logitech C270 HD Webcam
5. Mouse and Keyboard
6. Monitor
7. DisplayPort connector

Steps:
1. Train Yolov5 on custom dataset on a laptop which use GPU to reduce training duration. 
2. Inference on Jetson Nano.

# Step 1: Train Yolov5
Firstly, the dataset is my custom dataset and annotated using Roboflow. 
The Yolo training is done at the Google Colab. 
The model is saved as a .pt file.
This pt file will be copy into the Jetson Nano.

# Step 2: Jetson Nano Inference
1. Create a conda environment and activate that environment.
  cd archi
