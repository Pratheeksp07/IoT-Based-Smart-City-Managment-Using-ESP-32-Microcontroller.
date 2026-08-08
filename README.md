# 🏙️ IoT-Based Smart City Management System Using ESP32

An IoT-based Smart City Management System developed using an **ESP32 microcontroller** to integrate smart parking, automatic street lighting, and intelligent waste management into a single system.

The project focuses on improving **parking management, energy conservation, waste disposal monitoring, and user accountability** through sensor-based automation.

---

## 🚀 Project Overview

The system consists of three major smart-city modules:

### 🚗 Smart Car Parking System
Monitors parking spaces and identifies available and occupied parking slots using sensors.

### 💡 Automatic Street Light System
Automatically controls street lights based on ambient light conditions using an LDR sensor.

- 🌙 During night → Street lights ON
- ☀️ During daytime → Street lights OFF

This helps reduce unnecessary electricity consumption.

### 🗑️ Smart Waste Management System
Provides controlled access to the smart dustbin using a password-protected servo mechanism.

The system also monitors waste disposal and identifies incorrect disposal of wet waste in the dry-waste section. A fine is generated for incorrect disposal and the fine details are recorded in an Excel sheet.

---

# 🎯 Objectives

- Develop an IoT-based smart city management system using ESP32.
- Monitor parking-slot availability automatically.
- Automate street lights based on day and night conditions.
- Reduce unnecessary energy consumption.
- Provide secure access to the smart dustbin using password authentication.
- Monitor proper waste segregation.
- Generate fines for incorrect waste disposal.
- Maintain fine records for monitoring and accountability.

---

# 🛠️ Components Used

## Hardware

- ESP32 Development Board
- Ultrasonic Sensors
- LDR Sensor
- Servo Motor
- LEDs / Street Light LEDs
- Buzzer
- Keypad / Password Input
- Waste Detection Sensors
- LCD/OLED Display
- Jumper Wires
- Breadboard
- Power Supply

## Software

- Arduino IDE
- Embedded C / Arduino C
- ESP32
- Sensor-based automation
- Excel for fine record management

---

# 🚗 Module 1: Smart Car Parking System

The smart parking module monitors the availability of parking spaces using sensors.

Each parking slot is monitored to determine whether a vehicle is present.

### Working

1. The sensor continuously monitors the parking slot.
2. When a vehicle enters a parking slot, the system detects its presence.
3. The corresponding slot is marked as occupied.
4. When the vehicle leaves, the slot becomes available again.
5. The system can be used to monitor parking availability in real time.

### Example

```text
Parking Slot
     |
     v
Sensor detects vehicle
     |
     +-------- Vehicle Present --------+
☀️ DAY
  |
  v
LDR detects sufficient light
  |
  v
Street Light OFF
🌙 NIGHT
  |
  v
LDR detects low light
  |
  v
Street Light ON
             ENTER PASSWORD
                    |
                    v
             Verify Password
               /          \
            Correct      Incorrect
              |              |
              v              v
        Servo Opens       Access Denied
              |
              v
        Dispose Waste
     |                                  |
     v                                  v
   OCCUPIED                         AVAILABLE
