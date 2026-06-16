# 4. Component Selection

## Overview

The Smart Farm Monitoring System requires carefully selected hardware components that balance performance, cost, power efficiency, and reliability. The system is designed around an ESP32-based IoT architecture for environmental monitoring and control in agricultural applications.

The following components have been selected for the initial implementation phase of the system.


## 4.1 ESP32 LOLIN (Wemos)

### Description

The ESP32 LOLIN board serves as the central processing and communication unit of the system.

### Reason for Selection

- Integrated Wi-Fi and Bluetooth connectivity
- Dual-core processing capability
- Low power consumption suitable for field deployment
- Multiple GPIOs for sensor integration
- Strong support for Arduino and PlatformIO ecosystems

### Role in System

- Reads sensor data
- Processes environmental information
- Handles Wi-Fi communication
- Sends data to cloud/dashboard
- Controls actuators (future irrigation system)


## 4.2 Soil Moisture Sensor

### Description

The soil moisture sensor is used to measure the water content in the soil.

### Importance in Agriculture

- Determines irrigation requirements
- Prevents overwatering and underwatering
- Improves water resource efficiency
- Supports precision irrigation strategies

### Role in System

- Provides real-time soil moisture data
- Sends analog/digital signals to ESP32
- Triggers irrigation decisions (future automation)


## 4.3 DHT22 Temperature and Humidity Sensor

### Description

The DHT22 sensor measures ambient temperature and relative humidity.

### Importance in Agriculture

- Supports crop health monitoring
- Helps detect disease-prone conditions
- Assists in greenhouse climate control
- Improves environmental analysis accuracy

### Role in System

- Provides temperature readings (°C)
- Provides humidity readings (%)
- Sends digital data to ESP32 via GPIO


## 4.4 Mini Water Pump

### Description

A small DC water pump is used as an actuator for irrigation control.

### Importance in System

- Enables automated irrigation (future phase)
- Demonstrates closed-loop control capability
- Supports precision water delivery

### Power Requirement

- Requires external power supply (5V–12V depending on pump type)
- Controlled via relay or MOSFET driver circuit

### Role in System

- Activates irrigation when soil moisture is low
- Controlled by ESP32 via relay module
- Forms foundation for smart irrigation system


## System Integration Summary

The selected components form a complete IoT monitoring and control system:

Sensor Layer:
- Soil Moisture Sensor
- DHT22 Sensor

↓
Edge Processing Layer:
- ESP32 LOLIN

↓
Actuation Layer:
- Mini Water Pump

↓
Communication Layer:
- Wi-Fi (ESP32)

↓
Cloud / Dashboard Layer:
- Future integration (MQTT / HTTP / Firebase)
