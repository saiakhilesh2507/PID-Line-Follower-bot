# ESP32 PID Line Follower Robot

## Introduction

This project is a high-speed autonomous line-following robot built using an **ESP32**, **RLS08 IR Sensor Array**, and **L298N Motor Driver**. The robot uses a PID control algorithm to continuously adjust motor speeds based on sensor feedback, allowing it to accurately track a line with smooth and responsive movement.

The system features automatic sensor calibration, line-loss recovery, and differential motor control, making it an excellent project for learning embedded systems, robotics, and control systems.

---

## Features

* PID-based line following
* Automatic sensor calibration on startup
* Real-time position tracking using the RLS08 sensor array
* Differential motor speed control
* Line-loss detection and recovery mechanism
* Safety stop after prolonged line loss
* Adjustable PID parameters for tuning
* ESP32 high-performance control platform

---

## Hardware Used

| Component           | Description                  |
| ------------------- | ---------------------------- |
| ESP32 Dev Board     | Main microcontroller         |
| RLS08 Sensor Array  | Line detection sensor module |
| L298N Motor Driver  | Dual H-Bridge motor driver   |
| DC Gear Motors      | Robot locomotion             |
| Robot Chassis       | Mechanical platform          |
| Li-ion Battery Pack | Power source                 |

---

## Working Principle

1. The RLS08 sensor array continuously reads the position of the line.
2. Sensor values are normalized using calibration data collected at startup.
3. A weighted average algorithm determines the line position.
4. The PID controller calculates the tracking error.
5. Motor speeds are adjusted dynamically through the L298N motor driver.
6. If the line is lost, the robot attempts recovery by turning in the previous direction.
7. After a predefined timeout, the robot safely stops.

---

## PID Parameters

```cpp
KP = 1.7
KD = 10.0
BASE_SPEED = 140
```

These values can be adjusted according to track conditions and robot speed requirements.
