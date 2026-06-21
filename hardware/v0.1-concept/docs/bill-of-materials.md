# 5. Bill of Materials (BOM)

## Overview

The Bill of Materials (BOM) defines all hardware components required for the development of the Smart Farm Monitoring System. It includes sensors, microcontrollers, actuators, and supporting electronic components used in the prototype implementation.

This BOM is designed for a low-cost, scalable IoT agricultural monitoring system based on the ESP32 platform.


## 5.1 Core Processing Unit

| Item | Component | Description | Quantity | Estimated Cost |
|------|----------|-------------|----------|----------------|
| 1 | ESP32 LOLIN (Wemos) | Dual-core microcontroller with Wi-Fi + Bluetooth | 1 | Low |


## 5.2 Environmental Sensors

| Item | Component | Description | Quantity | Estimated Cost |
|------|----------|-------------|----------|----------------|
| 2 | DHT22 Sensor | Measures temperature and humidity | 1 | Low |
| 3 | Soil Moisture Sensor | Measures soil water content | 1 | Low |


## 5.3 Actuation Components

| Item | Component | Description | Quantity | Estimated Cost |
|------|----------|-------------|----------|----------------|
| 4 | Mini DC Water Pump | Used for irrigation control (future automation) | 1 | Low |
| 5 | Relay Module (5V) | Controls pump switching via ESP32 | 1 | Low |


## 5.4 Supporting Electronics

| Item | Component | Description | Quantity | Estimated Cost |
|------|----------|-------------|----------|----------------|
| 6 | Jumper Wires | Electrical connections between modules | Set | Low |
| 7 | Breadboard | Prototyping circuit assembly | 1 | Low |
| 8 | Resistors (10kΩ) | Pull-up / signal stabilization | Few | Very Low |
| 9 | Power Supply (5V/12V) | Powers pump and system | 1 | Medium |


## 5.5 System Cost Summary

| Category | Description |
|----------|-------------|
| Total Components | ~8–10 items |
| Cost Level | Low-cost prototype system |
| Target Use | Research + Educational + Prototype Development |


## Summary

The selected components provide a cost-effective and scalable foundation for an IoT-based Smart Farm Monitoring System. The BOM supports environmental sensing, edge processing, wireless communication, and basic actuation capabilities, making it suitable for both research and future agricultural deployment.

