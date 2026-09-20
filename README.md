# Himmat Stride — Wearable Gait Analysis System

## Overview

Himmat Stride is an IoMT-based wearable sensing platform designed for biomechanical gait analysis, rehabilitation tracking, and motion analysis.

The system uses multiple MPU6050 IMU sensor nodes with ESP32 controllers to collect lower-limb motion data and transmit the measurements to a central processing unit.

## System Architecture

```text
6× IMU Sensor Nodes
(Foot, Shank, Thigh)
        ↓
      ESP32
        ↓
   BLE / Wi-Fi
        ↓
 Central Waist Unit
        ↓
 Host Device / Web Application
        ↓
    Gait Analysis
    Hardware
ESP32 / ESP32-S3 Mini
MPU6050 6-axis IMU
Central waist-mounted hub
I2C communication
BLE / Wi-Fi communication
Sensor Nodes
Left Foot
Right Foot
Left Shank
Right Shank
Left Thigh
Right Thigh
Optional pelvis / CoG node
Firmware

The ESP32 firmware:

Initializes the MPU6050 through I2C
Reads accelerometer and gyroscope data
Uses a 50 Hz sampling rate
Packages sensor measurements into telemetry packets
Outputs data in CSV format
Sensor Configuration
Accelerometer: ±8g
Gyroscope: ±500°/s
Filter Bandwidth: 21 Hz
Sampling Rate: 50 Hz
Python Software

A Python simulation script is included to generate multi-node IMU gait-session data and save it as a CSV dataset.

Gait Parameters

The system is designed to support analysis of:

Step Length
Step Time
Cadence
Stance Phase
Swing Phase
Hip Angle
Knee Angle
Ankle Angle
Range of Motion (ROM)
Angular Velocity
Gait Symmetry
Technologies
C++
Python
ESP32
MPU6050
I2C
BLE / Wi-Fi
Embedded Systems
IMU-Based Motion Sensing
Project Focus

Wearable Sensors → Motion Data Acquisition → Wireless Telemetry → Gait Analysis
