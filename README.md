# Object-Detection-For-Autonomous-Vehicle-Jetson-Nano-
![detection-inference](https://user-images.githubusercontent.com/73321317/184523962-cdc3f439-8109-432c-aef8-8d1d54136a6a.jpg)

This is my project for Deep Learning in Intelligent Video Analytics and Computer Vision Workshop in IIUM.

This project is an object detection for autonomous vehicles using the Yolov5 deployed at the Jetson Nano. The framework used is the Pytorch and the training of the model will be done in Google Colab. 
Video

# Hardware Requirement:
![jetson-nano](https://user-images.githubusercontent.com/73321317/184523855-dccd188b-28bd-459e-a13c-0118a0ed8810.jpg)
1. Jetson Nano
2. 5V DC Barrel jack (or Micro-USB power supply)
3. MicroSD card (32GB UHS-1 minimum recommended)
4. Logitech C270 HD Webcam
5. Mouse and Keyboard
6. Monitor
7. DisplayPort connector


# Steps:
1. Train a Yolov5 on custom dataset on a laptop using Google Colab.
2. Jetson Nano setup. 
3. Inference on Jetson Nano.

## Step 1: Train Yolov5
Firstly, the dataset is a custom dataset and annotated using Roboflow. 
The Yolo training is done at the Google Colab, as in the Train_Yolov5_object_detection.ipynb. 
The model is saved as a pt file.
This pt file will be copy into the Jetson Nano for inference later.

## Step 2: Jetson Nano setup
### 2a) Clone Yolo
1. Create a conda environment with python version 3.8 and activate that environment.
2. Create a folder for the project and cd into the folder.
3. Clone the Yolo repository: `git clone https://github.com/ultralytics/yolov5` and cd into the yolov5 `cd yolov5/`
4. Open the requirements.txt and add '#' at the leftmost line of torch and torchvision and save the file. 
> #torch>=1.7.0 #torchvision>=0.8.1
5. Install the requirements: `pip install -r requirements.txt`

### 2b) Install PyTorch for GPU
1. Git clone the pytorch repo: `git clone --recursive --branch 1.7 http://github.com/pytorch/pytorch`
2. Cd into the pytorch folder: `cd pytorch/`
3. Install the requirements: `python3.8 -m pip install -r requirements.txt`
4. Run the setup.py: `python3.8 setup.py install`

### 2c) Install Torchvision for GPU
1. Pre-install some required lib `sudo apt-get install libjpeg-dev zlib1g-dev libpython3-dev libavcodec-dev libavformat-dev libswscale-dev`
2. Git clone the torchvision repo: `git clone --branch v0.5.0 https://github.com/pytorch/vision torchvision`
3. Cd into the vision folder: `cd torchvision/`
4. Run the setup.py: `python setup.py install`

## Step 3: Jetson Nano Inference
1. Activate the environment.
2. Cd into the yolov5 directory.
3. Copy the trained yolo file from step 1 which is the pt file and paste into the "models" folder under the "Yolov5" directory.
4. Run the inference: `python detect.py --weights ./models/model.pt --conf 0.45 --source 0` 
#model.pt is the name of the model
#conf is the min confidence level for detection 
#source 0 will use the webcam
#source image.jpg for image
#video.mp4 for video                                   

Link to [video](https://youtu.be/CpH7HJcMdg4)
