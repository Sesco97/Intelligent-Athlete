# Intelligent-Athlete

## Table of Contents 
- [Introduction](#introduction "Goto introduction")
- [Technologies](#technologies "Goto technologies")
- [Proof of Concept](#proof-of-concept "Goto proof-of-concept")

## Introduction 
The goal of this project is to develop a classifier to keep track of the exercises performed by an athlete during a workout session. In particular, we have considered the following exercises:
* [Push Press](https://www.youtube.com/watch?v=iaBVSJm78ko)
* [Shoulder Press](https://www.youtube.com/watch?v=5yWaNOvgFCM)
* [Push Jerk](https://www.youtube.com/watch?v=V-hKuAfWNUw)
* [Sit-Up](https://www.youtube.com/watch?v=_HDZODOx7Zw)
* [L-Up](https://www.youtube.com/watch?v=6Yd8-XEVj4M)
* [V-Up](https://www.youtube.com/watch?v=7UVgs18Y1P4)

The classifier takes as input data collected by the accelerometer and gyroscope of [two identical sensors](https://mbientlab.com/store/metamotions-p/) placed on the right wrist and the right ankle of the athlete. The classification pipeline is the following:
1. **Data Pre-Processing**: collected data are aligned through a synchronization logic and filtered through a low-pass filter to reduce the noise. Then, gravity and user acceleration are split. Finally, the [sliding window approach](https://www.geeksforgeeks.org/window-sliding-technique/) is implemented by splitting the signals into (overlapping) windows and extracting relevant features associated to them.
2. **Binary Classification**: a binary classifier is used to discriminate between periods of activity and periods of rest.
3. **Multiclass Classifier**: given a period of activity, the multiclass classifier labels such period with the correct exercise label.

The whole pipeline is represented in the following block diagram:

![pipeline](https://github.com/Sesco97/Intelligent-Athlete/assets/133167830/6c20eed7-2f2f-4d69-a66b-a6d50a98a40c)

**I personally contributed to this project by both implementing the sliding window approach (step 1) and developing the multiclass classifier (step 3)**.

Moreover, an Android app has been developed as a visualization tool for results (see [Proof of Concept](#proof-of-concept "Goto proof-of-concept")).

## Technologies
This project has been created with:

* Python 3.9 (classification logic);
* Android Studio and Chaquopy (Android app).

## Proof of Concept 
The following video is a demonstration of how the Android app works. While the athlete is performing a workout, the app analyzes the collected data and prints the final classification results.

https://github.com/Sesco97/Intelligent-Athlete/assets/133167830/55c1611c-1c6d-4961-a93a-efcd4184c99b



