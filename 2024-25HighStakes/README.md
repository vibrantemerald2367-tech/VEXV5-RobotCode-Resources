# VEX V5 Robotics Program for 2024-25 High Stakes

Autonomous and driver control programs for 2024-25 High Stakes VEX Robotics V5 competition.

## 🤖 Robot Overview

This program controls a VEX robot with the following components:

### Hardware Configuration
- **Drivetrain**: 4-motor tank drive (Ports 20, 14, 3, 19)
- **Ring Mechanism**: Motor group "GetRing" (Ports 11, 12) 
- **Digital Output**: Pneumatic/solenoid control "DigitalOutF" (Port 6)
- **Controller**: Primary controller for driver control
(you can change these port assignments according to actual needs)

## 🎮 Control Features

### Autonomous Routine
The autonomous program performs a complex sequence including:
- **Ring collection and scoring** using the GetRing mechanism
- **Precise navigation** with timed movements and turns
- **Pneumatic control** for mechanism actuation
- **Multi-stage scoring** routine

### Driver Control
- **Tank-style driving** with joystick control (up-down and left-right)
- **Ring mechanism control** with R1/R2 buttons
- **Pneumatic toggle** with Up/Down buttons
- **Velocity control** based on position of joystick input

## 📁 Program Structure

### Autonomous Mode
- **Initialization**: Sets up motors and pneumatics
- **Movement Sequence**: Pre-programmed path for competition
- **Scoring Actions**: Ring manipulation and delivery
- **Precision Control**: Timed waits and velocity adjustments

### Driver Control Mode
- **Controller Mapping**: 
  - Left/Right sticks: Tank drive
  - R1/R2: Ring mechanism control
  - Up/Down: Pneumatic output control
- **Real-time Control**: Responsive joystick input

## ⚙️ Configuration

### Motor Settings
- Drivetrain: 4 Omni wheels, 2 Traction wheels, 1:1.2 gear ratio
- Ring mechanism: Custom motor group with reversed motors
- Velocity control: Position-based speed adjustment

### Sensor Setup
- Digital output for pneumatic/solenoid control

## 🎯 Competition Use

### Autonomous Strategy
The autonomous routine is designed for:
- Consistent scoring in the 15-second period ONLY
- Reliable ring collection and placement
- Field navigation with precise turning

### Driver Control
- Smooth acceleration and deceleration
- Intuitive control layout
- Reliable mechanism operation

*This README file was generated with AI and edited afterwards, please report any errors if found. Thank you for your cooperation*
