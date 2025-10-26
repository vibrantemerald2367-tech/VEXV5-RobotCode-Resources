# VEX V5 Robotics Program for 2024-25 High Stakes

![VEX Robotics](https://img.shields.io/badge/VEX-V5-red?style=for-the-badge&logo=robot)
![License](https://img.shields.io/badge/License-GPL%203.0-green?style=for-the-badge)

Autonomous and driver control programs for 2024-25 High Stakes VEX Robotics V5 competition. This repository contains code for robot control using VEX V5 hardware.

## 🤖 Robot Overview

This program controls a VEX robot with the following components:

### Hardware Configuration
- **Drivetrain**: 4-motor tank drive (Ports 20, 14, 3, 19)
- **Ring Mechanism**: Motor group "GetRing" (Ports 11, 12) 
- **Digital Output**: Pneumatic/solenoid control "DigitalOutF" (Port 6)
- **Controller**: Primary controller for driver control

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

## 🚀 Quick Start

### Prerequisites
- VEX V5 Robot Brain
- VEXcode V5 software
- Compatible VEX robotics hardware (you will have to design and build this yourself as I am not sharing my design ideas here)

### Installation
1. Download this project file
2. Open in VEXcode V5
3. Configure hardware ports to match your robot
4. Upload to VEX Brain

### Hardware Setup
Ensure your robot is wired according to these port assignments (or you can change them according to actual needs):
Drivetrain: Ports 20, 14, 3, 19
GetRing Motors: Ports 11, 12
Digital Output: Port 6

## 📁 Program Structure

### Autonomous Mode
- **Initialization**: Sets up motors and pneumatics
- **Movement Sequence**: Pre-programmed path for competition (please note that values may vary depending on individual motors, use this for reference only)
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
- Consistent scoring in the 15-second period
- Reliable ring collection and placement
- Field navigation with precise turning

### Driver Assistance
- Smooth acceleration and deceleration
- Intuitive control layout
- Reliable mechanism operation

## 📄 License

Copyright (C) 2025 vibrantemerald2367-tech

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.

## 📧 Contact

**Developer**: vibrantemerald2367-tech  
**Email**: vibrantemerald.2367@gmail.com

---

*Developed for VEX Robotics Competition using VEXcode Pro Blocks*

*This README file was generated with AI and edited afterwards, please report any errors if found. Thank you for your cooperation*
