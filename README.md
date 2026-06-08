# Smart Farm Monitoring System

## Overview

The Smart Farm Monitoring System is an IoT-based research and development project focused on creating a low-cost, cloud-connected device for collecting and analyzing agricultural data.

The goal is to develop an integrated monitoring station capable of measuring weather, soil, and crop conditions in real time and transmitting the data to a cloud platform where farmers can access insights and make informed decisions.

This project is inspired by modern precision agriculture systems and aims to provide an affordable solution suitable for small-scale and medium-scale farmers.


## Project Goals

- Collect weather data from the farm environment.
- Collect soil condition data.
- Monitor crop health indicators.
- Transmit data to the cloud in real time.
- Store and visualize farm data through dashboards.
- Generate actionable insights for farmers.
- Explore machine learning applications for forecasting and decision support.


## Planned Features

### Weather Monitoring

- Air temperature
- Relative humidity
- Rainfall
- Atmospheric pressure
- Wind speed
- Wind direction
- Solar radiation

### Soil Monitoring

- Soil moisture
- Soil temperature
- Soil pH
- Electrical conductivity (EC)

### Crop Monitoring

- Canopy temperature
- Light exposure
- Growth indicators

### Connectivity

- Wi-Fi
- LoRa
- GSM/4G (future)

### Cloud Services

- Data storage
- Real-time monitoring
- Alert notifications
- Data analytics


## System Architecture

```text
Sensors
   │
   ▼
ESP32 Controller
   │
   ▼
Communication Layer (Wi-Fi / LoRa / GSM)
   │
   ▼
Cloud Platform
   │
   ▼
Dashboard & Analytics
   │
   ▼
Farmer


## Technology Stack

### Hardware

- ESP32
- Environmental Sensors
- Soil Sensors
- Solar Power System
- Battery Backup


### Software

- Embedded C
- PlatformIO
- Git
- GitHub


### Cloud

- Arduino IoT Cloud
- MQTT
- Firebase (under evaluation)


# Repository Structure

smart-farm-monitoring-system/
│
├── .gitignore
├── README.md
│
├── firmware/
│   ├── platformio.ini
│   ├── src/
│   │   └── main.cpp
│   ├── include/
│   ├── lib/
│   └── test/
│
├── hardware/
│   └── v1_sensor_node/
│       └── wiring.md
│
├── research/
│   ├── 01-problem-statement.md
│   ├── 02-requirements.md
│   └── 03-system-design.md
│
├── docs/
│   ├── setup-guide.md
│   ├── architecture.md
│   └── api-reference.md
│
├── data/
│   └── sample-readings.csv
│
├── images/
│   ├── wiring-diagram.png
│   └── system-architecture.png
│
└── project-management/
├── milestones.md
├── roadmap.md
└── tasks.md



## Development Roadmap

### Phase 1: Research

- Define farmer requirements  
- Study existing smart farming solutions  
- Evaluate sensors  
- Select communication technologies  


### Phase 2: Prototype

- Build ESP32 weather station  
- Integrate environmental sensors  
- Upload data to the cloud  


### Phase 3: Soil Monitoring

- Add soil moisture sensing  
- Add soil temperature monitoring  
- Develop irrigation recommendations  


### Phase 4: Advanced Analytics

- Data visualization  
- Alert generation  
- Machine learning experiments  


## Current Status

 Research Phase


## Author

**Ezra Keumbu Asiago**

Diploma in Electrical and Electronic Engineering  
Passionate about Embedded Systems, IoT, Automation, and Smart Agriculture.
