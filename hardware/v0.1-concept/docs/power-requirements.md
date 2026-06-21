# 2. Power Requirements

## Overview

The Smart Farm Monitoring System is powered from a standard 240V AC mains supply through a regulated 12V DC power supply. The power subsystem is responsible for supplying stable and reliable power to the monitoring, control, and irrigation components of the system.

A DC-DC buck converter is used to generate a regulated 5V supply for the ESP32 and relay module, while the ESP32 onboard regulator provides the required 3.3V supply for the connected sensors.

The power architecture is designed to support future expansion, including additional sensors, actuators, irrigation zones, and environmental control devices.


## Power Architecture

The system power flow is illustrated below:

240V AC Mains
        │
        ▼
12V DC Power Supply
(12V, 16A)
        │
        ├─────────────► Water Pump
        │
        ▼
DC-DC Buck Converter
(12V → 5V)
        │
        ▼
ESP32 LOLIN
        │
        ├── DHT22 Sensor
        ├── Soil Moisture Sensor
        └── Relay Module


## Primary Power Supply

The system uses a regulated DC power supply with the following specifications:

| Parameter              | Specification |
| ---------------------- | ------------- |
| Input Voltage          | 240V AC       |
| Output Voltage         | 12V DC        |
| Maximum Output Current | 16A           |
| Maximum Output Power   | 192W          |

The power supply serves as the primary energy source for all system components.

### Power Calculation

Power = Voltage × Current
Power = 12V × 16A
Power = 192W

The available power capacity significantly exceeds the current system requirements and provides sufficient headroom for future expansion.

## Voltage Distribution

The system operates using three voltage levels.

### 12V Rail

The 12V rail is supplied directly by the primary power supply.

Used by:

* Mini Water Pump
* Future 12V actuators
* Future cooling fans
* Future expansion modules

### 5V Rail

A DC-DC buck converter reduces the 12V supply to a regulated 5V output.

Used by:

* ESP32 LOLIN (VIN/USB equivalent supply)
* Relay Module

### 3.3V Rail

The ESP32 onboard voltage regulator generates the 3.3V supply required by the sensors.

Used by:

* DHT22 Temperature and Humidity Sensor
* Soil Moisture Sensor


## Power Consumption

### Monitoring and Control Subsystem

| Component                  | Typical Current Consumption |
| -------------------------- | --------------------------: |
| ESP32 LOLIN (Wi-Fi Active) |                      240 mA |
| DHT22 Sensor               |                      2.5 mA |
| Soil Moisture Sensor       |                        5 mA |
| Relay Module               |                       70 mA |
| **Total**                  |                **≈ 318 mA** |

### Irrigation Subsystem

| Component       | Typical Current Consumption |
| --------------- | --------------------------: |
| Mini Water Pump |                 300–1000 mA |

The actual current consumption of the water pump depends on the selected model and operating conditions.


## Power Regulation

### DC-DC Buck Converter

A buck converter is used to efficiently reduce the 12V supply voltage to 5V.

**Recommended Module**

* LM2596 Adjustable Buck Converter

**Configuration**

| Parameter      | Value  |
| -------------- | ------ |
| Input Voltage  | 12V DC |
| Output Voltage | 5V DC  |
| Output Current | ≥ 1A   |

The buck converter provides efficient voltage regulation while minimizing power loss and heat generation.


## Grounding Strategy

All low-voltage components share a common ground reference.

Connected grounds include:

* ESP32 Ground
* DHT22 Ground
* Soil Moisture Sensor Ground
* Relay Module Ground
* Water Pump Ground
* 12V Power Supply Ground

A common ground ensures stable measurements, reliable communication, and proper relay operation.


## Protection and Safety

The following protection measures are incorporated into the design:

* Common grounding of all system components.
* Relay isolation between control and load circuits.
* Dedicated high-current power path for the water pump.
* 10 kΩ pull-up resistor on the DHT22 data line.
* Regulated voltage supplies for all electronic components.
* Physical separation between low-power control circuits and high-current actuator circuits.

### Recommended Future Enhancements

* Input fuse protection.
* Reverse polarity protection.
* Power distribution terminal block.
* Power status indicator LED.
* Surge protection for field deployments.


## Scalability

The 12V, 16A power supply provides substantial unused capacity, allowing future integration of:

* Additional soil sensors.
* Environmental monitoring sensors.
* Multiple irrigation pumps.
* Solenoid valves.
* Ventilation fans.
* Greenhouse lighting systems.
* Edge computing and communication modules.

No major modifications to the power subsystem will be required for moderate future expansion.


## Summary

The Smart Farm Monitoring System utilizes a regulated 12V, 16A DC power supply as its primary energy source. A DC-DC buck converter generates a stable 5V supply for the ESP32 and relay module, while the ESP32 onboard regulator provides the required 3.3V supply for connected sensors. The architecture ensures reliable operation, efficient power distribution, electrical safety, and sufficient capacity for future system expansion.


