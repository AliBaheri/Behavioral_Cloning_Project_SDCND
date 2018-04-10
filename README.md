## **Behavioral Cloning** 

<p align="center">
<img width="400" src="https://github.com/AliBaheri/BehavioralCloning_April2018/blob/master/video.gif"/>


**Behavioral Cloning Project**

The goals / steps of this project are the following:
* Use the simulator to collect data of good driving behavior
* Build, a convolution neural network in Keras that predicts steering angles from images
* Train and validate the model with a training and validation set
* Test that the model successfully drives around track one without leaving the road
* Summarize the results with a written report

### My project includes the following files:
* `model.py` containing the script to create and train the model
* `drive.py` for driving the car in autonomous mode
* `model.h5` containing a trained convolution neural network 
* `README.md` containing the report


### Overall hardware setup:

<p align="center">
<img width="500" src= "https://github.com/AliBaheri/P3-Writeup/blob/master/images/overal_hw.png">
(Image credit: Nvidia paper)

### Overall software setup:

<p align="center">
<img width="600" src= "https://github.com/AliBaheri/P3-Writeup/blob/master/images/overal_sw.png">
(Image credit: Nvidia paper)

### Data

During the training, the simulator captures data with a frequency of 10hz. In fact, at a given time step it recorded three images taken from left, center, and right cameras:

<p align="center">
<img width="800" src= "https://github.com/AliBaheri/P3-Writeup/blob/master/images/cameras.png">


### Model Architecture and Training Strategy

The model is based on Nvidia architecture with more dropout layers to prevent overfitting. To deal with a large amount of data, I used data generator to train the model. The images have also been processed using the brightness, shadow augmentation, and flip images techniques using openCV libraries.


<p align="center">
<img width="350" src= "https://github.com/AliBaheri/P3-Writeup/blob/master/images/model.png">

The model utilizes dropout layers to prevent overfitting. The train/validation/test splits have been used in `get_log()`. The model parameters are `batch_size=64` and n`num_epoch=20`. I also used the `Adam` optimizer to optimize the loss function. The model was trained in AWS EC2 from Amazon.

### Conclusion
While the results are sasitfactory for the first track, the car is not able to successfully run in the second (jungle) track. My plan is to revisit this project to find a solution for the second track. Furthermore, training a deep reinforcement learning agent would be an intresting future direction.

