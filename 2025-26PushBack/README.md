# VEX V5 Robotics Program for 2025-26 Push Back

Autonomous and driver control programs for 2025-26 Season Push Back VEX Robotics V5 competition  
**Season**: V5RC PushBack (2025-2026)  
**Language**: VEXcode V5 (Blocks, can convert to Python/C++ once you download it)

---

## 🤖 Robot Overview

This repository contains competition-ready autonomous and driver control programs for the 2025-26 VEX Robotics Competition season, *Push Back*. The robot is designed for **goal scoring**, **descoring + competing for Control Zone**, and **parking** in the Park Zone.

### Hardware Configuration

| Component | Type | Port(s) | Notes |
|-----------|------|---------|-------|
| BL (Left Drivetrain) | Motor Group | 2, 10 | Tank drive left side |
| BR (Right Drivetrain) | Motor Group | 11, 20 | Tank drive right side |
| HighRoller | Motor | 8 | Top intake/roller to transport scoring objects to Lift |
| LowRoller | Motor Group | 1, 7 | Bottom intake/roller |
| RearRoller | Motor | 9 | Rear mechanism for scoring attached to Lift |
| Lift | Pneumatic (Digital Out) | B | Controls lift mechanism to adapt for different Goal heights |
| Door | Pneumatic (Digital Out) | A | Controls door for colour-sorting |
| Hook | Pneumatic (Digital Out) | C | Controls hook for descoring and scoring in the Long Goal |
| BumperH | Bumper Switch | H | Bumper sensor for positioning when collecting scoring objects from Loaders |
| Optical15 | Optical Sensor | 15 | Color sensing for scoring object counting and selecting |

### Controller Mapping

| Control | Function |
|---------|----------|
| Left Stick (Axis 3) | Forward/Backward (tank drive left) |
| Right Stick (Axis 1) | Turning (tank drive differential) |
| R1 | Stop rollers (toggle) |
| R2 | Reverse both rollers |
| X | Reverse top roller, forward bottom roller |
| Up Button | Lift up (release) |
| Down Button | Lift down (engage) |
| Left Button | Hook extend |
| Y Button | Hook retract |
| L1 | RearRoller forward |
| L2 | RearRoller reverse (score from back) |

---

## 📁 Program Files

| File | Description |
|------|-------------|
| `Right4Long.v5blocks` | Autonomous + Driver code — scores 4 rings in long goal + pushes into control zone (10 bonus points) |
| `(C+L)Right.v5blocks` | Autonomous + Driver code — scores **both centre goal AND long goal** |
| `RedRight(frontcentre).v5blocks` | Autonomous + Driver code — scores centre goal only |
| `SkillsRLong.v5blocks` | Robot Skills program — fills long goal completely and parks at end |

---

## 🎮 Autonomous Routines

**Please note that the field setup is symmetrical, so although only Red Alliance code is provided here, the Blue Alliance code should be the same, with a few number changes due to slight errors on field setup**

### Right4Long — 4 scored in Long Goal + Push
RearRoller backspin (200°) — preload positioning

Drive forward (760° @ 50% speed)

Run rollers forward (1 sec)

Lift down (Door closed)

Turn right (343° @ 30%)

Drive onto loader (BumperH triggered)

Wiggle sequence to align/intake

Return to long goal (-710°)

RearRoller forward (2 sec)

Final positioning and hook toggle

**Scoring**: 4 scored in long goal + control zone push (10 bonus)

### C+L Right — Centre + Long Goal
Preload spin-up (200°)

Forward 270°

Rollers forward, turn 435°

Position for centre goal (250° turn)

Score centre goal (reverse rollers)

Reposition for long goal

Final scoring sequence

**Scoring**: Both centre and long goal rings

### RedRight(frontcentre) — Centre Goal Only
Forward 710° @ 50%

Rollers forward (1 sec)

Turn right (345°)

BumperH loader approach

4× wiggle scoring cycles

Return path (-710°)

Final positioning and RearRoller scoring

**Scoring**: Centre goal only (simpler, faster auton)

### SkillsRLong — Robot Skills Autonomous (Long Goal Full)
Half field navigation

Complete one long goal filling

End-of-match parking

Optimized for maximum points

**Note**: Designed specifically for Robot Skills Challenge format

---

## 🎮 Driver Control Features

### Tank Drive System
- 4-motor tank drive: `BLFlag = Axis3 + Axis1`, `BRFlag = Axis3 - Axis1`
- Smooth velocity control based on joystick position

### Roller Control Logic
- **Default state**: Both HighRoller and LowRoller spin forward (intaking)
- **R1**: Toggle rollers OFF (flag system)
- **R2**: Both rollers reverse (outtake)
- **X**: Top roller reverse, bottom roller forward (differential output) FOR CENTER GOAL ONLY

### Pneumatic Controls
- **Up/Down**: Lift mechanism (for different heights of goals)
- **Left/Y**: Hook extend/retract (for descoring, scoring in Control Zone)

### RearRoller Control
- **L1/L2**: Forward/reverse for back-of-robot scoring mechanism

---

## ⚙️ Custom Functions

### `myblockfunction_speedLeft_speedRight_degrees()`
Custom motion function that drives the robot a specified distance using encoder feedback on the right side (BR). Supports both forward and reverse movement.

**Parameters**:
- `speedLeft`: Left motor group velocity (%)
- `speedRight`: Right motor group velocity (%)
- `Degrees`: Distance to travel (positive = forward, negative = backward)

---

## 🔧 Robot-Specific Notes

### Motor Groups
- **BL** (Left Drive): Ports 2 & 10
- **BR** (Right Drive): Ports 11 & 20
- **LowRoller**: Ports 1 & 7

### Pneumatics
All pneumatics use digital out ports:
- Door: Port A
- Lift: Port B
- Hook: Port C

### Sensors
- **BumperH (Port H)**: Used for precise positioning against Loaders only
- **Optical15 (Port 15)**: Used in some versions for scoring object counting (Skills)

---

## 🏆 Competition Strategy

### Autonomous Win Point (AWP) Compliance
Programs are designed to meet AWP requirements as much as possible:
- 3+ scored objects of alliance color
- 2 goals on alliance side with rings
- Robot depart from Park Zone
- Robot does not cross center line

### Skills Strategy
- `SkillsRLong` optimized for maximum points in 60-second Autonomous Skills Match
- Focuses on long goal filling + parking bonus

---

## 📝 Configuration Adjustments

To adapt these programs for your robot:

1. **Update port assignments** in the VEXcode configuration
2. **Adjust degree values** in autonomous routines based on your robot's wheel diameter and gear ratio
3. **Tune speeds** (`speedLeft/speedRight` variables) for your robot's weight and drivetrain
4. **Modify wiggle sequences** for different Loader mechanisms

---

## ⚠️ Important Notes

- These programs are **specific to our team's robot design** (motor orientations, pneumatic configurations, sensor placements)
- The `myblockfunction` assumes the **right encoder (BR)** is used as the primary distance sensor
- All autonomous routines use **encoder-based positioning** — ensure encoders are calibrated (however different motors may have different setups so please change the values according to your specific needs)
- Pneumatic states assume normally open/closed configurations — verify before competition

---

## 📚 References

- [V5RC Push Back Game Manual](https://content.vexrobotics.com/docs/25-26/v5rc-push-back/docs/Push-Back-4.0.pdf)
- VEX V5 Robotics Competition official rules

---

## 🙏 Credits

**Developer**: vibrantemerald2367-tech

*Last Updated: May 2026*

---

*This README file was generated with AI and edited afterwards, please report any errors if found. Additionally, if you have any inquiries, please contact me at this email address: vibrantemerald.2367@gmail.com*

*I realise that it is difficult to utilise these codes without a robot design, so if in need, please drop me an email or open an issue in this repository to let me know and I may attach a CAD file of our team's robot design. Many thanks*
