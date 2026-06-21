# 6. Pin Assignment

## Overview

This document defines the GPIO assignments used in the Smart Farm Monitoring System. Proper pin allocation ensures reliable sensor integration, efficient data acquisition, and future system scalability.

The ESP32 LOLIN serves as the central processing unit and interfaces with environmental sensors and actuator control circuits.


## 6.1 ESP32 GPIO Assignment Table

| Component                         | Signal         | ESP32 Pin | Pin Type           |
| --------------------------------- | -------------- | --------- | ------------------ |
| DHT22                             | Data           | GPIO 4    | Digital Input      |
| Soil Moisture Sensor              | Analog Output  | GPIO 34   | Analog Input (ADC) |
| Relay Module (Water Pump Control) | Control Signal | GPIO 26   | Digital Output     |
| Status LED (Optional)             | Control Signal | GPIO 2    | Digital Output     |


## 6.2 DHT22 Temperature and Humidity Sensor

### Connection Details

| DHT22 Pin | Connection |
| --------- | ---------- |
| VCC       | 3.3V       |
| DATA      | GPIO 4     |
| GND       | GND        |

### Additional Requirement

A 10 kΩ pull-up resistor should be connected between:

* DATA
* 3.3V

This ensures stable communication between the sensor and the ESP32.


## 6.3 Soil Moisture Sensor

### Connection Details

| Soil Moisture Pin  | Connection |
| ------------------ | ---------- |
| VCC                | 3.3V       |
| GND                | GND        |
| AO (Analog Output) | GPIO 34    |

### Notes

GPIO 34 is an input-only ADC pin and is suitable for analog sensor measurements.

The ESP32 converts the analog voltage into a digital value representing soil moisture levels.


## 6.4 Water Pump Control Circuit

### Relay Module Connection

| Relay Pin | Connection |
| --------- | ---------- |
| VCC       | 5V         |
| GND       | GND        |
| IN        | GPIO 26    |

### Pump Power Circuit

The water pump should not be connected directly to the ESP32.

Instead, the ESP32 controls the relay module, which switches power to the pump.

Power Flow:

External Power Supply
↓
Relay Module
↓
Mini Water Pump

This protects the ESP32 from excessive current draw.


## 6.5 Power Distribution

### ESP32 Power

| Source          | Connection     |
| --------------- | -------------- |
| USB Cable       | ESP32 USB Port |
| External Supply | VIN Pin        |

### Sensor Power

| Device               | Supply Voltage |
| -------------------- | -------------- |
| DHT22                | 3.3V           |
| Soil Moisture Sensor | 3.3V           |

### Actuator Power

| Device          | Supply Voltage              |
| --------------- | --------------------------- |
| Relay Module    | 5V                          |
| Mini Water Pump | 5V–12V (depending on model) |


## 6.6 Pin Utilization Summary

| ESP32 Pin | Purpose               |
| --------- | --------------------- |
| GPIO 4    | DHT22 Data            |
| GPIO 26   | Relay Control         |
| GPIO 34   | Soil Moisture Sensor  |
| GPIO 2    | Status LED (Optional) |
| 3.3V      | Sensor Power          |
| GND       | Common Ground         |


## Summary

The selected pin assignments provide a simple and scalable hardware configuration for the Smart Farm Monitoring System. The design supports reliable environmental monitoring while providing a foundation for future expansion, including additional sensors, cloud connectivity, automated irrigation control, and advanced decision-support capabilities.

