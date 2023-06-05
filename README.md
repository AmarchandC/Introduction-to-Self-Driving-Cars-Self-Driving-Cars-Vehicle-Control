# Introduction to Self-Driving Cars: Self-Driving Vehicle Control (Project Report)
The final project in the first  course in the Self Driving Car specialization offered by Coursera.


Objective: To write and implement a controller for the CARLA simulator. The goal is to control the vehicle to follow a race track by navigating through preset waypoints. The vehicle needs to reach these waypoints at certain desired speeds, so both longitudinal and lateral control will be required.

#Part 1: Longitudinal Vehicle control.

A simple PID controller was implemented for the longitudinal control of the vehicle. 
The desired speed was the reference input for the controller. The ouputs by the controller were throllle and brake positions. Vehicle is designed to perform longitudinal as well as lateral control (longitudinal speed and steering input). 

**1. Vehicle Longitudinal Control Mechanism**

PID controller is used to control the longitudinal vehicle speed. The reference input is the desired speed (target speed), the controller basically tries to minimize the difference between the current speed and the target speed.

There are Proportional, Integral and Derivative components in a PID controller. K_P K_I and K_D are the corresponding gains.

The prportional controller multiplies the velocity error (difference in the actual and target velocities) by the proportional gain. This makes sure that the correction of velocity happens in the right direction. An issue with using only a proportional controller is that, when the errors become too small, the corrections become insignificant for any value of K_P, failing to get a zero steady state error.

The integral controller tries to rectify the steady state error issue of the proportional controller by accumulating all the errors, thus not letting the velocity error become too small.

The derivative controller is sensitive to the high rate of variation of the error. This helps in dampening the overshoot.
![PID long control](https://github.com/AmarchandC/Introduction-to-Self-Driving-Cars-Self-Driving-Cars-Vehicle-Control/assets/82858194/328596e6-9eec-4324-a1b3-d869e13f0539)








