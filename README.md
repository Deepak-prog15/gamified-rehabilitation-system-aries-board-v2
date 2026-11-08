# Gamified Neuro-Rehabilitation System (VEGA ARIES & ESP32)

An intelligent, sensor-driven rehabilitation platform combining wearable sensor telemetry with gamified biofeedback for upper-extremity physical therapy and motor re-education.

---

## 🌟 Overview

This platform integrates real-time IMU kinematic tracking (BNO08x / MPU6050) with interactive gamified exercises. It supports both the indigenous **C-DAC VEGA ARIES (THEJAS32 RISC-V)** microcontroller platform and **ESP32** IoT architectures.

### Key Capabilities:
* **Interactive Rehabilitation Games**: Flight navigation, marble maze, and target tracking designed for active range-of-motion (ROM).
* **Kinematic Joint Tracking**: Real-time roll, pitch, and yaw tracking for arm circumduction, bicep curls, and wrist flex/extension.
* **Biometric & Repetition Counter**: Automated repetition counting with velocity thresholds and smoothness analysis.
* **Multi-Platform Embedded Firmware**: Native firmware modules for VEGA ARIES RISC-V and ESP32.

---

## 📁 Repository Structure

```
Rehabilitation-gamified-main/
├── vega_aries_firmware/         # C-DAC VEGA ARIES (RISC-V) embedded firmware
│   ├── bicep_curl_counter/      # Repetition counter with IMU kinematics
│   ├── bno08x_raw_test/         # BNO08x sensor validation test bench
│   └── vega_aries_i2c_scanner/  # I2C peripheral scanner for ARIES boards
├── esp32_firmware/              # ESP32 IoT sensor firmware
│   ├── arm_rehab_serial_imu/    # High-speed serial IMU stream
│   ├── arm_rehab_trainer/       # Standalone trainer module
│   ├── bicep_curl_counter/      # WebSocket-enabled bicep curl counter
│   └── force_sensor_test/       # Analog force/flex sensor test bench
├── rehab_system/                # Python Desktop Rehab System & 3D Games
│   ├── exercises/               # Exercise definitions and repetition logic
│   ├── games/                   # Gamified therapy modules (flight, marble maze)
│   ├── models/                  # 3D anatomical arm and hand models
│   ├── sensors/                 # Sensor clients (Serial, WebSocket, Simulator)
│   ├── ui/                      # PyQt / Web clinical interfaces & telemetry graphs
│   └── main_with_game.py        # Central application launcher
├── arm_tracker/                 # Web-based upper-extremity arm tracking interface
├── hand_rehab/                  # Web-based hand therapy interface
└── ARIESv2 0_Datasheet_v2 .pdf  # Technical datasheet for ARIES v2.0 board
```

---

## 🚀 Quick Start Guide

### 1. Prerequisites
* **Python 3.8 - 3.11** installed.
* Install required dependencies:
  ```bash
  cd rehab_system
  pip install -r requirements.txt
  ```

### 2. Launching the Rehabilitation System
To start the central rehabilitation dashboard and interactive games:
```cmd
cd rehab_system
START.bat
```
*(Or run `python main_with_game.py`)*

### 3. VEGA ARIES Firmware Flashing
* Open the Arduino IDE configured with the **VEGA ARIES Board Support Package (BSP)**.
* Load any sketch from `vega_aries_firmware/` (e.g., `bicep_curl_counter`).
* Connect the VEGA ARIES v2.0 board via USB and upload.

