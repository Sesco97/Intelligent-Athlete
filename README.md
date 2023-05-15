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

The classifier takes as input the data collected by the accelerometer and gyroscope of [two identical sensors](https://mbientlab.com/store/metamotions-p/) placed on the right wrist and the right ankle of the athlete. The classification pipeline is the following:
1. **Data Pre-Processing**: collected data are aligned through a synchronization logic and filtered through a low-pass filter to reduce the noise. Then, gravity and user acceleration are split. Finally, the [sliding window approach](https://www.geeksforgeeks.org/window-sliding-technique/) is implemented by splitting the signals into (overlapping) windows and extracting relevant features associated to them.
2. **Binary Classification**: a binary classifier is used to discriminate between periods of activity and periods of rest.
3. **Multiclass Classifier**: given a period of activity, the multiclass classifier labels such period with the correct exercise label.

<p align="center">
  <img src="https://user-images.githubusercontent.com/80259549/140044672-219e3161-75cc-4742-83b2-076b59213233.png" />
</p>

## Technologies

## Proof of Concept 
