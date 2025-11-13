Temperature Controlled Fan – Arduino-based Real-Life Embedded Project
A. GitHub Repository Link

(Add your link after creating the repo)
Repository: https://github.com/your-username/Temperature-Controlled-Fan

B. Project Overview

This project implements a real-life automatic temperature-controlled fan system using an Arduino and a temperature sensor (DHT11 / DHT22 / LM35).
The fan automatically increases speed when the temperature rises and slows or turns off when it becomes cooler.

This embedded solution is commonly used in:

Home automation

Cooling cabinets

Server rooms

Smart ventilation systems

The code is designed professionally with:

Non-blocking logic (millis())

Hysteresis-based fan switching

PWM fan speed control

Serial command interface

Modular and scalable architecture

C. Hardware Used

Arduino UNO / Nano / Mega

DHT11 / DHT22 temperature sensor (or LM35 analog sensor)

DC Fan (5V/12V)

N-channel MOSFET / Motor Driver

External power supply for fan

Jumper wires

Breadboard

D. Block Diagram
 Temperature Sensor (DHT/LM35)
             |
             v
   ┌──────────────────┐
   │   Arduino UNO     │
   │ - Reads sensor    │
   │ - Computes PWM    │
   │ - Controls fan    │
   └──────────────────┘
             |
             v
      MOSFET Driver
             |
             v
          DC FAN

E. Features
✔ 1. Automatic Fan Control

Fan turns ON once temperature crosses a threshold (default: 30°C).

✔ 2. PWM Fan Speed Control

Fan speed automatically scales based on how hot it gets.

✔ 3. Hysteresis Logic

Prevents rapid ON/OFF switching.

✔ 4. Non-Blocking Code

Allows future expansion (sensors, displays, communication).

✔ 5. Serial Commands

Users can:

View temperature

Change threshold

View fan status

Check mode (DHT / LM35)

Example command:

s28.5   → sets new threshold to 28.5°C

F. Circuit Connections
If using DHT11/DHT22
DHT Signal → D2  
VCC → 5V  
GND → GND

If using LM35
LM35 Output → A0  
VCC → 5V  
GND → GND

Fan Driver
Arduino Pin 9 (PWM) → Gate of MOSFET  
MOSFET Drain → Fan –  
Fan + → External Supply (5V/12V)  
External Supply GND → Arduino GND  


⚠ NEVER connect a DC fan directly to Arduino pins.

G. Folder Structure
Temperature-Controlled-Fan/
│
├── src/
│   └── Temperature_Controlled_Fan.ino
│
├── README.md
├── LICENSE
│
├── docs/
│   └── circuit_diagram.png   (optional)
│
└── QA/
    ├── ISSUES_LOG.md
    └── QA_workflow.md

H. Code Summary

Uses millis() for non-blocking timing

Supports DHT OR LM35 sensors (selectable via USE_DHT flag)

Serial interface for easy debugging

PWM output on pin 9 for fan control

Temperature threshold adjustable at runtime

I. How to Use
1. Upload Code

Open Temperature_Controlled_Fan.ino in Arduino IDE → Upload.

2. Open Serial Monitor

Set:

9600 baud

Both NL & CR

3. Test Commands
p → Print status  
t → Show threshold  
s30 → Set threshold to 30°C  
m → Show mode (DHT/LM35)
h → Help

J. QA Issues Logged

Example issues created in GitHub:

Sensor reading inconsistency (DHT)

PWM fan not starting at low speeds

Add OLED display for UI (enhancement)

Improve wiring documentation

Add serial threshold saving to EEPROM

Full list is inside QA/ISSUES_LOG.md.

K. Collaboration Summary

Team members commented on GitHub Issues

Pull Requests opened for:

Documentation fixes

Code improvements

Additional safety checks

Code reviewed and merged into the main branch

QA workflow documented in QA_workflow.md

L. Learning Outcomes

Implemented a real-life automation system

Practiced sensor interfacing (digital/analog)

Used non-blocking embedded programming

Used GitHub for:

Issue tracking

Collaboration

Pull requests

QA documentation

Prepared professional engineering documentation
