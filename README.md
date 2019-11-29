# VEHICLE DETECTION, TRACKING AND COUNTING
This sample project focuses on "Vechicle Detection, Tracking and Counting" using [**TensorFlow Object Counting API**](https://github.com/ahmetozlu/tensorflow_object_counting_api). 

---
--

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/36344830-095cc4ec-1431-11e8-8e57-976c40d87cf9.gif">
</p>

---

***The developing is on progress! This sample project will be updated soon, the more talented traffic analyzer app will be available in this repo!***

---

## General Capabilities of This Sample Project

This sample project has more than just counting vehicles, here are the additional capabilities of it:

- Recognition of approximate vehicle color
- Detection of vehicle direction of travel
- Prediction the speed of the vehicle
- Prediction of approximate vehicle size
- **The images of detected vehicles are cropped from video frame and they are saved as new images under "[detected_vehicles](https://github.com/ahmetozlu/vehicle_counting_tensorflow/tree/master/detected_vehicles)" folder path**
- **The program gives a .csv file as an output ([traffic_measurement.csv](https://github.com/ahmetozlu/vehicle_counting_tensorflow/blob/master/traffic_measurement.csv)) which includes "Vehicle Type/Size", " Vehicle Color", " Vehicle Movement Direction", " Vehicle Speed (km/h)" rows, after the end of the process for the source video file.**

The input video can be accessible by this [link](https://github.com/ahmetozlu/vehicle_counting_tensorflow/blob/master/sub-1504614469486.mp4).

## Theory

### System Architecture

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/35445395-8dba4406-02c2-11e8-84bf-b480edbe9472.jpg">
</p>

- Vehicle detection and classification have been developed using TensorFlow Object Detection API, [see](https://github.com/ahmetozlu/vehicle_counting_tensorflow/blob/master/vehicle_detection_main.py) for more info.
- Vehicle speed prediction has been developed using OpenCV via image pixel manipulation and calculation, [see](https://github.com/ahmetozlu/vehicle_counting_tensorflow/tree/master/utils/speed_and_direction_prediction_module) for more info.
- Vehicle color prediction has been developed using OpenCV via K-Nearest Neighbors Machine Learning Classification Algorithm is Trained Color Histogram Features, [see](https://github.com/ahmetozlu/vehicle_counting_tensorflow/tree/master/utils/color_recognition_module) for more info.

[TensorFlow™](https://www.tensorflow.org/) is an open source software library for numerical computation using data flow graphs. Nodes in the graph represent mathematical operations, while the graph edges represent the multidimensional data arrays (tensors) communicated between them.

[OpenCV (Open Source Computer Vision Library)](https://opencv.org/about.html) is an open source computer vision and machine learning software library. OpenCV was built to provide a common infrastructure for computer vision applications and to accelerate the use of machine perception in the commercial products.

### Tracker

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/41812993-a4b5a172-7735-11e8-89f6-083ec0625f21.png" | width=700>
</p>

Source video is read frame by frame with OpenCV. Each frames is processed by ["SSD with Mobilenet" model](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17) is developed on TensorFlow. This is a loop that continue working till reaching end of the video. The main pipeline of the tracker is given at the above Figure.

### Model

<p align="center">
  <img src="https://user-images.githubusercontent.com/22610163/48481757-b1d5a900-e81f-11e8-824b-4317115fe5b4.png">
</p>

By default I use an ["SSD with Mobilenet" model](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17) in this project. You can find more information about SSD in [here](https://towardsdatascience.com/understanding-ssd-multibox-real-time-object-detection-in-deep-learning-495ef744fab). See the [detection model zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md) for a list of other models that can be run out-of-the-box with varying speeds and accuracies.

## Project Demo

Demo video of the project is available on [My YouTube Channel](https://www.youtube.com/watch?v=PrqnhHf6fhM).

## Installation

**1.) Python and pip**

Python is automatically installed on Ubuntu. Take a moment to confirm (by issuing a python -V command) that one of the following Python versions is already installed on your system:

- Python 3.3+

The pip or pip3 package manager is usually installed on Ubuntu. Take a moment to confirm (by issuing a *pip -V* or *pip3 -V* command) that pip or pip3 is installed. We strongly recommend version 8.1 or higher of pip or pip3. If Version 8.1 or later is not installed, issue the following command, which will either install or upgrade to the latest pip version:

    $ sudo apt-get install python3-pip python3-dev # for Python 3.n
    
**2.) OpenCV**

See required commands to install OpenCV on Ubuntu in [here](https://gist.github.com/dynamicguy/3d1fce8dae65e765f7c4).

**3.) TensorFlow**

Install TensorFlow by invoking one of the following commands:

    $ pip3 install tensorflow     # Python 3.n; CPU support (no GPU support)
    $ pip3 install tensorflow-gpu # Python 3.n; GPU support

**4.) TensorFlow Object Detection API**

See required commands to install TensorFlow Object Detection API on Ubuntu in [here](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md).
  
If you are still getting problem about installation after completed the installation of the packet that are given above, please check that [link](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md) out to get detailed info about installation.

---
- After completing these 4 installation steps that are given at above, you can test the project by this command:

      python3 vehicle_detection_main.py
    }

