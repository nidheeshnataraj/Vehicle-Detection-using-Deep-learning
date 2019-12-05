# VEHICLE DETECTION, TRACKING AND COUNTING
This sample project focuses on "Vechicle Detection, Tracking and Counting" using [**TensorFlow Object Counting API**](https://github.com/ahmetozlu/tensorflow_object_counting_api). 

---
--

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/36344830-095cc4ec-1431-11e8-8e57-976c40d87cf9.gif">
</p>

## General Capabilities of This Project
- Recognition of approximate vehicle color
- Detection of vehicle direction of travel
- Prediction the speed of the vehicle
- Prediction of approximate vehicle size

## Theory

### System Architecture

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/35445395-8dba4406-02c2-11e8-84bf-b480edbe9472.jpg">
</p>

- Vehicle detection and classification have been developed using TensorFlow Object Detection API,
- Vehicle speed prediction has been developed using OpenCV via image pixel manipulation and calculation, .
- Vehicle color prediction has been developed using OpenCV via K-Nearest Neighbors Machine Learning Classification Algorithm is Trained Color Histogram Features

[TensorFlow™]is an open source software library for numerical computation using data flow graphs. Nodes in the graph represent mathematical operations, while the graph edges represent the multidimensional data arrays (tensors) communicated between them.

[OpenCV (Open Source Computer Vision Library)]is an open source computer vision and machine learning software library. OpenCV was built to provide a common infrastructure for computer vision applications and to accelerate the use of machine perception in the commercial products.

### Tracker

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/41812993-a4b5a172-7735-11e8-89f6-083ec0625f21.png" | width=700>
</p>

Source video is read frame by frame with OpenCV. Each frames is processed by ["SSD with Mobilenet" model](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17) is developed on TensorFlow. This is a loop that continue working till reaching end of the video. The main pipeline of the tracker is given at the above Figure.

### Model

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/48481757-b1d5a900-e81f-11e8-824b-4317115fe5b4.png">
</p>

By default I use an ["SSD with Mobilenet" model] in this project ## Installation

**1.) Python and pip**

Python is automatically installed on Ubuntu. Take a moment to confirm (by issuing a python -V command) that one of the following Python versions is already installed on your system:

- Python 3.3+

The pip or pip3 package manager is usually installed on Ubuntu. Take a moment to confirm (by issuing a *pip -V* or *pip3 -V* command) that pip or pip3 is installed. We strongly recommend version 8.1 or higher of pip or pip3. If Version 8.1 or later is not installed, issue the following command, which will either install or upgrade to the latest pip version:

    $ sudo apt-get install python3-pip python3-dev # for Python 3.n
    
**2.) OpenCV**

See required commands to install OpenCV on Ubuntu 

**3.) TensorFlow**

Install TensorFlow by invoking one of the following commands:

    $ pip3 install tensorflow     # Python 3.n; CPU support (no GPU support)
    $ pip3 install tensorflow-gpu # Python 3.n; GPU support
  

---
- After completing these 3 installation steps that are given at above, you can test the project by this command:

      python3 vehicle_detection_main.py
    }

