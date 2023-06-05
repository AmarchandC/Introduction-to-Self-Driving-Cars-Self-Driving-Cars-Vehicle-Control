# Introduction to Self-Driving Cars: Self-Driving Vehicle Control (Project Report)
The final project in the first  course in the Self Driving Car specialization offered by Coursera.


Objective: To write and implement a controller for the CARLA simulator. The goal is to control the vehicle to follow a race track by navigating through preset waypoints. The vehicle needs to reach these waypoints at certain desired speeds, so both longitudinal and lateral control will be required.

#Part 1: Longitudinal Vehicle control.

A simple PID controller was implemented for the longitudinal control of the vehicle. 
The desired speed was the reference input for the controller. The ouputs by the controller were throllle and brake positions. Vehicle is designed to perform longitudinal as well as lateral control (longitudinal speed and steering input). 

1. Vehicle Longitudinal Control Mechanism
PID controller is used to control the longitudinal vehicle speed. The reference input is the desired speed (target speed), the controller basically tries to minimize the difference between the current speed and the target speed.

There are Proportional, Integral and Derivative components in a PID controller. Kp K_D
![PID long control](https://github.com/AmarchandC/Introduction-to-Self-Driving-Cars-Self-Driving-Cars-Vehicle-Control/assets/82858194/328596e6-9eec-4324-a1b3-d869e13f0539)








