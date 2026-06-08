# Wiring Diagram Smart Farm Monitoring System (Mark 1)

## Overview

This document explains how the sensors are connected to the ESP32 microcontroller for the first prototype (Mark 1).


## Wiring Diagram

Soil Sensor ─── GPIO 34
        │
DHT22 ─────── GPIO 4
        │
        ▼
      ESP32
        │
     USB Cable
        │
     Laptop (Serial Monitor)


## Explanation

### Soil Moisture Sensor

- Connected to GPIO 34  
- Reads soil moisture as an analog value  
- Helps determine irrigation needs  


### DHT22 Sensor

- Connected to GPIO 4  
- Measures:
  - Temperature  
  - Humidity  


### ESP32 Microcontroller

- Central processing unit of the system  
- Reads data from sensors  
- Sends data to computer (Serial Monitor)  


### USB Connection

- Used for power supply  
- Used for uploading code  
- Used for reading live sensor data  

  

  


