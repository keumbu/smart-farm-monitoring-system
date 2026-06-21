# Design Decisions

## Overview

This document records the key engineering decisions made in the Smart Farm Monitoring System (v0.1 concept stage). It explains why specific hardware, power architecture, sensors, and system design approaches were selected.

The goal is to ensure clarity, maintainability, and scalability for future development.


## 1. Microcontroller Selection

### Selected: ESP32 LOLIN

**Reason:**
- Built-in Wi-Fi for IoT connectivity
- Sufficient GPIO for sensors and relay control
- Low power consumption
- Compatible with Arduino IDE and PlatformIO
- Supports future expansion (cloud, OTA updates, AI integration)

**Alternatives Considered:**
- Arduino Uno (no Wi-Fi, limited memory)
- ESP8266 (fewer GPIO pins)


## 2. Power Architecture

### Selected: 12V DC main supply with 5V regulation

**Reason:**
- 12V supports higher current loads (especially pump)
- Suitable for long cable runs in farm environments
- Efficient step-down to 5V using buck converter (LM2596)
- ESP32 safely powered via regulated 5V input

**Power Distribution:**
- 12V → Water pump (actuation system)
- 5V → ESP32 + relay module
- 3.3V → Sensors (via ESP32 regulator)


## 3. Sensor Selection

### Soil Moisture Sensor (Capacitive Type)

**Reason:**
- Corrosion-resistant compared to resistive sensors
- Stable long-term soil measurement
- Suitable for outdoor deployment


### DHT22 Temperature & Humidity Sensor

**Reason:**
- Measures both temperature and humidity
- Simple digital interface
- Good accuracy for agricultural monitoring


## 4. Actuation System

### Selected: Relay-controlled DC Water Pump

**Reason:**
- Provides electrical isolation between ESP32 and pump
- Simple ON/OFF irrigation control
- Easy GPIO integration

**Alternative Considered:**
- MOSFET driver (more efficient but more complex implementation)


## 5. Communication System

### Selected: Wi-Fi (ESP32 Native)

**Reason:**
- No external communication module required
- Enables cloud integration and remote monitoring
- Supports MQTT, HTTP APIs, and dashboards


## 6. Grounding Strategy

### Selected: Common Ground System

**Reason:**
- Ensures stable sensor readings
- Prevents signal noise
- Required for relay switching stability

**Rule:**
All components (ESP32, sensors, relay, pump supply) share a common ground reference.


## 7. System Architecture Approach

### Selected: Modular Architecture

**System Modules:**
- Sensor subsystem
- Processing subsystem (ESP32)
- Actuation subsystem (relay + pump)
- Power subsystem

**Reason:**
- Easier debugging and maintenance
- Supports future scaling (multiple zones, additional sensors)
- Clear separation of system responsibilities


## 8. Future Expansion Considerations

The system is designed to support future upgrades:

- Soil pH and EC sensors
- NPK nutrient monitoring
- Multiple irrigation zones
- Solar power integration
- Cloud dashboards and mobile notifications
- AI-based irrigation recommendations


## Summary

The Smart Farm Monitoring System is designed as a modular and scalable IoT platform. The selected components and architecture prioritize reliability, simplicity, and future extensibility toward advanced smart agriculture and AI-driven farming systems.
