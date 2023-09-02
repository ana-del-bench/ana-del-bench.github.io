---
layout: project
type: project
image: img/posture_monitor/sensor_closeup.png
title: "Postural Monitoring Device"
date: 2021
published: true
labels:
  - Robotics
  - Arduino
  - C++
  - CAD Design
summary: "A wearable digital posture monitor I developed for my STEM capstone project."
---

<div class="text-center p-4">
  <img width="200px" src="../img/posture_monitor/monitor_whole.PNG" class="img-thumbnail" >
  <img width="200px" src="../img/posture_monitor/sensor_closed.png" class="img-thumbnail" >
  <img width="200px" src="../img/posture_monitor/sensor_closeup.png" class="img-thumbnail" >
</div>

The goal of this capstone project was to develop a wearable device specifically for dancers as a way to get digital feedback on proper the alignment technique needed for more technical forms of dancing like ballet.

This was an independent STEM capstone project that I designed using CAD modeling, programming, and circuitry skills to connect a system of gyro sensors and small motors used to create vibrations.

The premise of the design was for the gyro sensors (used to collect movement and and rotation data) to continuously track movement and keep track of their positioning in relation to the other gyro sensors in the network. When the readings were determined to be "out-of alignment" with each other the small motors would vibrate to alert the wearer.

This idea was based off of the more common posture monitors used by office workers to promote proper sitting posture when working at a desk. However, the smaller attachments track positioning in a dynamic matter (rather than the less adaptable algorithms used for sitting still at a desk) tailoring the device towards dancers.

The network of sensors was connected via a multiplexer which is used to allow multiple input signals (i.e. the four gyro sensors) to share one device (i.e. the arduino hardware). Below is some of the code used for the multiplexer network, as well as the algorithms used to convert the gyro sensor input for position tracking.


```cpp
MPU6050 mpu1 = MPU6050(); //channel 1
MPU6050 mpu2 = MPU6050(); //channel 0 (broken)
MPU6050 mpu3 = MPU6050(); //channel 3
MPU6050 mpu4 = MPU6050(); //channel 7

double tempVals[10];
double error = 0.1;

extern "C" { 
  #include "utility/twi.h" // from Wire library, so we can do bus scanning
}

#define TCAADDR 0x70

double integrateVals (double accelVals[10]) { //use acceleration to find velocity (Trapezoidal Rule - Estimation)
 double newInt = 0;
 for (int i = 1; i < 10; i++) {
 newInt = newInt + ((accelVals[i-1]+accelVals[i])/2);
 } 
 return (newInt * 0.005);
}

double secIntVals (double velOne, double velTwo) { //Use velocity values to find position (Trapezoidal Rule)
 double newPos;
 newPos = ((velOne+velTwo)/2);
 return newPos;
}
```
