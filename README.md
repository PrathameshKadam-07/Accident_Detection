# 🚗 Accident Detection System using Raspberry Pi

A real-time accident detection and emergency alert system built using Raspberry Pi, MPU6050 sensor, GSM module, and Python. This IoT-based project aims to improve road safety by immediately notifying emergency contacts with the location details when a crash is detected.

---

## 📌 Overview

This system monitors a vehicle’s motion through accelerometer and gyroscope data. Upon detecting sudden impact or abnormal movement, the system:
- Identifies the accident using sensor data,
- Captures the GPS location (optional),
- Sends an alert SMS to a predefined emergency contact via the GSM module.

> Built and tested using Raspberry Pi, this project demonstrates a scalable, low-cost solution to enhance road safety and minimize response time during accidents.

---

## ⚙️ Features

- 🚨 **Accident Detection** using MPU6050 sensor (accelerometer + gyroscope)
- 📡 **Real-time SMS Alerts** via SIM800L GSM module
- 🌍 **Location Tracking** with GPS module (optional)
- 🔧 **Modular Python Codebase** with SMS, sensor, and logic separated
- 🧪 **Tested Unit Scripts** for accelerometer and GSM communication
- 💡 **Scalable IoT Design** adaptable to smart vehicle ecosystems

---

## 🧩 Hardware Components

| Component           | Description                                      |
|---------------------|--------------------------------------------------|
| Raspberry Pi        | Central microcontroller unit                     |
| MPU6050 Sensor      | Accelerometer + gyroscope                        |
| SIM800L GSM Module  | Sends SMS alerts to emergency contact            |
| GPS Module (optional)| Sends location coordinates with the alert       |
| Breadboard & Wires  | Prototyping setup                                |
| Power Supply        | For Raspberry Pi and modules                     |

---

## 🧪 Software Stack

- **Python 3**
- [`smbus`](https://pypi.org/project/smbus/) – for I2C communication with MPU6050  
- [`pyserial`](https://pypi.org/project/pyserial/) – for GSM serial communication  
- Linux (Raspberry Pi OS or similar)



