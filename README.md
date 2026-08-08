# Robotic Arm Model

## 📌 Project Overview

This project presents the design and development of a **4-DOF robotic arm model** controlled using two dual-axis joysticks and an Arduino microcontroller.

The robotic arm uses four servo motors to control different movements of the arm. The current position of each servo is stored in the Arduino EEPROM so that the arm can resume from its previous position after restarting.

## ⚙️ Features

- 4 servo motor controlled robotic arm
- Dual-axis joystick control
- Independent control of four robotic arm movements
- Servo position storage using EEPROM
- Position recovery after restarting the Arduino
- Serial Monitor support for debugging
- Adjustable servo movement using joystick input

## 🛠️ Components Used

- Arduino
- 4 × Servo Motors
- 2 × Dual-Axis Joysticks
- Robotic Arm Mechanical Structure
- Connecting Wires
- Power Supply

## 🔌 Pin Configuration

| Component | Arduino Pin | EEPROM Address |
|---|---:|---:|
| Gripper Servo | D6 | 0 |
| Up/Down Servo | D9 | 1 |
| Front/Back Servo | D11 | 2 |
| Neck Servo | D10 | 3 |
| Joystick 1 - X Axis | A0 | — |
| Joystick 1 - Y Axis | A1 | — |
| Joystick 2 - X Axis | A2 | — |
| Joystick 2 - Y Axis | A3 | — |

## 🧠 Working Principle

The two joysticks provide analog input values through pins A0, A1, A2, and A3.

The Arduino reads these values using `analogRead()`.

- Joystick 1 X-axis → Gripper
- Joystick 1 Y-axis → Up/Down movement
- Joystick 2 X-axis → Front/Back movement
- Joystick 2 Y-axis → Neck movement

When the joystick value is above `700`, the corresponding servo position is increased.

When the joystick value is below `300`, the corresponding servo position is decreased.

The servo position is maintained within a safe range and stored in EEPROM.

## 💾 EEPROM Position Storage

Each servo has a dedicated EEPROM address:

```text
EEPROM Address 0 → Gripper
EEPROM Address 1 → Up/Down
EEPROM Address 2 → Front/Back
EEPROM Address 3 → Neck
