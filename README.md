# Object-Detection-For-Autonomous-Vehicle-Jetson-Nano-
This is my project for Deep Learning in Intelligent Video Analytics and Computer Vision Workshop in IIUM.

This project is an object detection for autonomous vehicles using the Yolov5 deployed at the Jetson Nano. The framework is the Pytorch and is run on Google Colab.  

#Hardware Requirement:
1. Jetson Nano 2GB
2. 5V DC Barrel jack (or Micro-USB power supply)
3. MicroSD card (32GB UHS-1 minimum recommended)
4. Logitech C270 HD Webcam
5. Mouse and Keyboard
6. Monitor
7. DisplayPort connector

Steps:
1. Train Yolov5 on custom dataset on a laptop which use GPU to reduce training duration.
2. Jetson Nano setup. 
3. Inference on Jetson Nano.

# Step 1: Train Yolov5
Firstly, the dataset is my custom dataset and annotated using Roboflow. 
The Yolo training is done at the Google Colab. 
The model is saved as a .pt file.
This pt file will be copy into the Jetson Nano.

# Step 2: Jetson Nano setup
##Clone Yolo
1. Create a conda environment with python version 3.8 and activate that environment.
2. Create a folder for the project and cd into the folder.
3. Clone the Yolo repository: `git clone https://github.com/ultralytics/yolov5` and cd into the yolov5 `cd yolov5/`
4. Open the requirements.txt and add '#' at the leftmost line of torch and torchvision. 
> #torch>=1.7.0 #torchvision>=0.8.1
5. Install the requirements: `pip install -r requirements.txt`

##Install PyTorch for GPU
1. Git clone the pytorch repo: `git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch`
2. Cd into the pytorch folder: `cd pytorch/`
3. Install the requirements: `python3.8 -m pip install -r requirements.txt`
4. Run the setup.py: `python3.8 setup.py install`

##Install Torchvision for GPU
1. Git clone the torchvision repo: `git clone https://github.com/pytorch/vision`
2. Cd into the vision folder: `cd vision/`
3. Git checkout: `git checkout v0.8.`
4. Run the setup.py: `python3 setup.py bdist_wheel`
5. Run the whl file: `python3 -m pip install dist/torchvision-0.8.0a0+291f7e2-cp38-cp38-linux_aarch64.whl`

# Step 3: Jetson Nano Inference
1. 
