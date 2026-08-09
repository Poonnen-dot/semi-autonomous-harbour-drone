# System Architecture

## Overview

The drone is designed as an integrated mechatronic system consisting of flight control, propulsion, power, navigation, communication, sensing, and payload subsystems.

## Major Subsystems

### 1. Flight Control
- Pixhawk 2.4.8
- ArduPilot firmware
- Mission Planner ground-control software

### 2. Propulsion
- S500 quadcopter frame
- Four 2212 920KV brushless motors
- Velox 50A 4-in-1 ESC
- 10 × 4.5 inch propellers

### 3. Power System
- 4S 6200 mAh LiPo battery
- Power distribution system
- Pixhawk power module

### 4. Navigation
- u-blox NEO-M9N GPS
- GPS-based position estimation
- Mission Planner waypoint planning

### 5. Communication
- FlySky FS-i6X transmitter
- FS-IA10B receiver
- T10 telemetry system

### 6. Sensing
- Benewake TFmini Plus range sensor
- GPS position data
- Flight-controller IMU and onboard sensors

### 7. Payload
- Payload mechanism designed for logistics applications

## High-Level Data Flow


                         Ground Station
                              │
                         Telemetry Link
                              │
                              ▼
GPS ──────────────────► Pixhawk 2.4.8 ◄──────── RC Receiver
                              │
                    ┌─────────┴─────────┐
                    │                   │
                    ▼                   ▼
               4-in-1 ESC          Range Sensor
                    │
             ┌──────┼──────┬──────┐
             ▼      ▼      ▼      ▼
            M1     M2     M3     M4
             │      │      │      │
             └──────┴──────┴──────┘
                       │
                  Propulsion

Battery ───────► Power Distribution
                       │
                       ├────► ESC
                       └────► Pixhawk Power Module
