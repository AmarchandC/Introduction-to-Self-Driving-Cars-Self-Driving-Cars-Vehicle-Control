# Introduction to Self-Driving Cars: Self-Driving Vehicle Control (Project Report)
The final project in the first  course in the Self Driving Car specialization offered by Coursera.


Objective: To write and implement a controller for the CARLA simulator. The goal is to control the vehicle to follow a race track by navigating through preset waypoints. The vehicle needs to reach these waypoints at certain desired speeds, so both longitudinal and lateral control will be required.

**part 1. Vehicle Longitudinal Control using a PID Controller**

A simple PID controller was implemented for the longitudinal control of the vehicle. 
The desired speed was the reference input for the controller. The ouputs by the controller were throllle and brake positions. Vehicle is designed to perform longitudinal as well as lateral control (longitudinal speed and steering input). 

![PID long control](https://github.com/AmarchandC/Introduction-to-Self-Driving-Cars-Self-Driving-Cars-Vehicle-Control/assets/82858194/328596e6-9eec-4324-a1b3-d869e13f0539)


PID controller is used to control the longitudinal vehicle speed. The reference input is the desired speed (target speed), the controller basically tries to minimize the difference between the current speed and the target speed.

There are Proportional, Integral and Derivative components in a PID controller. K_P, K_I and K_D are the corresponding gains.

The prportional controller multiplies the velocity error (difference in the actual and target velocities) by the proportional gain. This makes sure that the correction of velocity happens in the right direction. An issue with using only a proportional controller is that, when the errors become too small, the corrections become insignificant for any value of K_P, failing to get a zero steady state error.

The integral controller tries to rectify the steady state error issue of the proportional controller by accumulating all the errors, thus not letting the velocity error become too small.

The derivative controller is sensitive to the high rate of variation of the error. This helps in dampening the overshoot.



**part 1. Vehicle Lateral Control**

Stanley controller was used to incorporate lateral control into the vehicle model. More information to Stanley Control is given in the link below: https://www.coursera.org/lecture/intro-self-driving-cars/lesson-3-geometric-lateral-control-stanley-bJoWh

In a lateral control algorithm, the two main objectives are to find the correct vehicle heading alignment and eliminating the offset to the path.
Stanley controller is a Geometric controller which takes care of the above objectives.

**Stanley Controller:**

Reference Point: Centre of the front axle of the vehicle

Two erros to minimize: 1. Error in heading, 2. Error in position relative to the closest point on the path.

The three main taks: Correct the heading error, correct the position error, and obey any rules regarding the steering angle limits/bounds. 

Before going into further details, we need to look at an important term: **Cross-track Error** 

**Cross-Track Error** is the lateral distance between the heading vector and the target point (closest point on the reference path).

![image](https://github.com/AmarchandC/Introduction-to-Self-Driving-Cars-Self-Driving-Cars-Vehicle-Control/assets/82858194/fe5c6c2c-11ba-412a-9aa1-374c6f5f0bfc)

![image](https://github.com/AmarchandC/Introduction-to-Self-Driving-Cars-Self-Driving-Cars-Vehicle-Control/assets/82858194/8634d708-2324-4211-9651-a9c811581ea5)


The steering correction given by the controller is composed of two terms. The first term accounts for the heading error, and is exaxtly the difference between the current heading direction and the desired heading direciton. 

The second terms accounts for the cross track error, eliminating the distance between the current position and the target point.









