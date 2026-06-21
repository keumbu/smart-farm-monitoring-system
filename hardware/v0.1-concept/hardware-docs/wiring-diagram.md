# 7. Wiring Diagram

## Overview

The Smart Farm Monitoring System is built around the ESP32 LOLIN microcontroller, which serves as the central processing and communication unit. The system integrates environmental sensors and an irrigation actuator to enable real-time agricultural monitoring and future automation capabilities.

The wiring design follows a modular architecture that simplifies installation, maintenance, troubleshooting, and future system expansion.


## 7.1 System Wiring Architecture

The hardware architecture consists of the following subsystems:

### Sensor Subsystem

Responsible for environmental and soil data acquisition.

Connected devices:

* DHT22 Temperature and Humidity Sensor
* Soil Moisture Sensor

### Processing Subsystem

Responsible for data acquisition, processing, and communication.

Connected device:

* ESP32 LOLIN Microcontroller

### Actuation Subsystem

Responsible for irrigation control.

Connected devices:

* Relay Module
* Mini Water Pump

### Power Subsystem

Responsible for supplying power to all system components.

Connected devices:

* USB Power Supply (ESP32)
* External Power Supply (Water Pump)


## 7.2 DHT22 Wiring

The DHT22 sensor is connected to the ESP32 through a digital communication interface.

### Connections

| DHT22 Pin | ESP32 Connection |
| --------- | ---------------- |
| VCC       | 3.3V             |
| DATA      | GPIO 4           |
| GND       | GND              |

### Additional Requirement

A 10 kΩ pull-up resistor is connected between:

* DATA
* 3.3V

This resistor ensures stable digital communication.


## 7.3 Soil Moisture Sensor Wiring

The soil moisture sensor provides analog measurements representing soil water content.

### Connections

| Soil Moisture Pin | ESP32 Connection |
| ----------------- | ---------------- |
| VCC               | 3.3V             |
| GND               | GND              |
| AO                | GPIO 34          |

The ESP32 reads the analog signal using its internal ADC (Analog-to-Digital Converter).


## 7.4 Relay Module Wiring

The relay module acts as an electrical switch controlled by the ESP32.

### Connections

| Relay Pin | ESP32 Connection |
| --------- | ---------------- |
| VCC       | 5V               |
| GND       | GND              |
| IN        | GPIO 26          |

The relay isolates the ESP32 from the higher current required by the water pump.


## 7.5 Water Pump Wiring

The water pump is powered from an external power source and switched through the relay module.

### Power Connections

| Water Pump Terminal | Connection          |
| ------------------- | ------------------- |
| Positive (+)        | Relay Output        |
| Negative (-)        | Power Supply Ground |

### Operation

When the ESP32 activates the relay:

ESP32
↓
Relay Activated
↓
Power Applied
↓
Water Pump Runs

When the relay is deactivated, power to the pump is disconnected.


## 7.6 Power Distribution

### ESP32 Supply

The ESP32 receives power through:

* USB connection
* VIN pin (external supply)

### Sensor Supply

The DHT22 and Soil Moisture Sensor operate from:

* 3.3V output from ESP32

### Pump Supply

The Mini Water Pump uses:

* Dedicated 5V–12V external power source

This prevents excessive current draw from the ESP32.


## 7.7 Wiring Safety Considerations

The following design practices are applied:

* Common ground shared by all components
* Relay isolation for actuator protection
* External power source for water pump
* Proper pull-up resistor for DHT22 communication
* Separation of low-power and high-current circuits

These measures improve system reliability and reduce the risk of hardware damage.


## 7.8 Wiring Diagram Reference

The complete wiring diagram is provided in:

* `hardware/0.1-concept/wiring-diagram/wiring-diagram.png`
* `hardware/v0.1-concept/wiring-diagram/wiring-diagram.svg`
* `hardware/v0.1-concept/wiring-diagram/wiring-diagram.drawio.xml`

The diagram visually illustrates all electrical connections between the ESP32, sensors, relay module, and water pump.


## Summary

The wiring configuration establishes a reliable hardware platform for environmental monitoring and irrigation control. The modular design allows additional sensors and actuators to be integrated with minimal modifications, supporting future expansion toward advanced Smart Farming and Precision Agriculture applications.


