# Smart Farm Monitoring System

![Status](https://img.shields.io/badge/status-active_development-orange)
![Platform](https://img.shields.io/badge/platform-ESP32-blue)
![Framework](https://img.shields.io/badge/framework-PlatformIO-green)
![Language](https://img.shields.io/badge/language-C++-blue)
![Architecture](https://img.shields.io/badge/architecture-IoT-success)

### IoT-Based Smart Agriculture Platform for Real-Time Environmental Monitoring

The Smart Farm Monitoring System is an ESP32-powered IoT platform designed to collect, process, and visualize environmental, soil, and crop data in real time. The system leverages cloud connectivity and data analytics to support smarter farming decisions and improve agricultural productivity.

## Research Title

Design and Implementation of an IoT-Based Smart Farming Monitoring System

## Project Overview

The Smart Farm Monitoring System is an IoT-based research and development project focused on creating a low-cost, cloud-connected device for collecting and analyzing agricultural data.

The goal is to develop an integrated monitoring station capable of measuring weather, soil, and crop conditions in real time and transmitting the data to a cloud platform where farmers can access insights and make informed decisions.

This project is inspired by modern precision agriculture systems and aims to provide an affordable solution suitable for small-scale and medium-scale farmers.


## MVP Features

### Weather Monitoring

- Air temperature monitoring
- Relative humidity monitoring
- Atmospheric pressure monitoring
- Light intensity monitoring
- Heat index calculation

### Soil Monitoring

- Soil moisture monitoring
- Soil temperature monitoring
- Soil condition analysis

### Data Collection

- Periodic sensor readings
- Real-time environmental monitoring
- Timestamped measurements
- Sensor status verification

### Data Logging

- CSV data storage
- Historical data recording
- Local data backup
- Data export support

### Alert System

- High temperature alerts
- Low temperature alerts
- Soil moisture warnings
- Sensor fault detection
- System status notifications

### Connectivity

- Wi-Fi connectivity
- Cloud data synchronization
- Remote device access
- Automatic network reconnection

### Dashboard Monitoring

- Real-time sensor visualization
- Historical trend charts
- Farm status overview
- Device health monitoring

### Firmware Features

- Modular software architecture
- Configuration management
- Error handling
- Sensor abstraction layer
- Over-the-air (OTA) update support

### System Reliability

- Automatic sensor recovery
- Automatic network recovery
- Continuous operation mode
- Fault-tolerant monitoring

### Documentation

- Hardware documentation
- Software documentation
- Wiring diagrams
- Installation guide
- User manual


## Project Goals

- Collect real-time environmental data from the farm, including weather conditions such as temperature, humidity, and atmospheric pressure.
- Monitor soil health parameters such as moisture levels, temperature, and nutrient-related indicators.
- Track crop health and growth conditions using environmental and sensor-based insights.
- Enable real-time data transmission from the farm to a cloud-based platform for remote access.
- Store, organize, and manage historical farm data for analysis and decision-making.
- Provide interactive dashboards for visualizing farm conditions and trends over time.
- Generate actionable insights to support farmers in improving productivity and resource management.
- Lay the foundation for predictive analytics and machine learning models for forecasting weather patterns, crop performance, and farm optimization.
- Develop a scalable IoT architecture that can be expanded with additional sensors and automation features in the future.


## System Architecture

The Smart Farm Monitoring System is designed using a modular IoT architecture that enables scalable, real-time environmental monitoring and data-driven decision-making.

### 1. Sensor Layer (Field Devices)
This layer consists of physical sensors deployed in the farm environment to collect real-time data.

- Weather sensors (temperature, humidity, pressure, light intensity)
- Soil sensors (moisture, temperature, pH, electrical conductivity)
- Crop monitoring sensors (optional expansion)

These sensors are connected to a microcontroller (ESP32/Arduino) for data acquisition.

### 2. Edge Processing Layer (Microcontroller Unit)
The microcontroller acts as the central processing unit at the edge.

- Reads data from all connected sensors
- Performs basic filtering and validation
- Executes local control logic (alerts, thresholds)
- Formats data for transmission

### 3. Communication Layer
Responsible for transmitting data from the farm to the cloud.

- Wi-Fi connectivity (ESP32-based)
- MQTT / HTTP protocol for data transfer
- Automatic reconnection handling
- Secure data transmission (future enhancement: TLS encryption)

### 4. Cloud Layer
This layer handles data storage and remote accessibility.

- Cloud database for real-time and historical data storage
- API endpoints for data access
- Data aggregation and processing services
- Scalability for multiple farm nodes

### 5. Application Layer (Dashboard & Analytics)
User-facing layer for visualization and decision-making.

- Real-time dashboard for monitoring farm conditions
- Graphical representation of historical trends
- Alert notifications and system status
- Mobile or web-based access

### 6. System Architecture Diagram

            +----------------------+
            |   Soil Sensors       |
            | (Moisture, pH, EC)   |
            +----------+-----------+
                       |
                       v

+------------------+ Data Collection +----------------------+
| Weather Sensors | ------------------> | |
| (Temp, Humidity, | | |
| Light, Rain) | | |
+------------------+ | ESP32 |
| (Edge Processing) |
+------------------+ | |
| Crop Sensors | ------------------> | |
| (Growth, Light) | | |
+------------------+ +----------+----------+
|
| Wi-Fi
v
+----------------------+
| Cloud Platform |
| (Firebase / MQTT DB) |
+----------+----------+
|
v
+----------------------+
| Dashboard |
| (Web / Mobile UI) |
+----------+----------+
|
v
+----------------------+
| User Insights |
| (Farm Decisions) |
+----------------------+        

### Note
The ESP32 acts as the edge computing unit, handling real-time sensor processing before transmitting data to the cloud for storage and visualization.

### 7. Data Flow Overview
Sensor data flows through the system as follows:

Sensors → Microcontroller (Edge Processing) → Wi-Fi Module → Cloud Database → Dashboard → User Insights

### 8. System Design Principles

- Modular and scalable architecture
- Low-cost hardware integration
- Real-time data processing capability
- Fault-tolerant communication system
- Expandable for AI/ML integration in future versions


## Hardware Overview

The Smart Farm Monitoring System is built around a modular ESP32-based IoT architecture designed for real-time environmental monitoring, cloud connectivity, and future agricultural automation. The hardware platform is designed to be scalable, allowing new sensors and control systems to be integrated as the project evolves.

### Microcontroller

The system uses a **LOLIN32 ESP32 Development Board** as the primary processing unit.

#### Key Features

- Dual-core 32-bit processor
- Integrated Wi-Fi and Bluetooth connectivity
- Low-power operation
- Multiple GPIO, ADC, I2C, SPI, and UART interfaces
- Suitable for real-time IoT applications

### Environmental Monitoring Sensors

The system supports environmental sensors for monitoring weather and climate conditions.

- BME280 — Temperature, humidity, and atmospheric pressure
- BH1750 — Ambient light intensity
- Rain Sensor — Rainfall detection
- Anemometer *(future expansion)* — Wind speed monitoring
- Wind Vane *(future expansion)* — Wind direction monitoring
- Solar Radiation Sensor *(future expansion)* — Solar energy measurement

### Soil Monitoring Sensors

The system supports a comprehensive set of soil monitoring sensors.

- Capacitive Soil Moisture Sensor — Soil moisture measurement
- DS18B20 — Soil temperature monitoring
- Soil pH Sensor *(future expansion)* — Soil acidity and alkalinity analysis
- Electrical Conductivity (EC) Sensor *(future expansion)* — Nutrient availability and salinity monitoring
- NPK Sensor *(future expansion)* — Nitrogen, phosphorus, and potassium analysis
- Soil Salinity Sensor *(future expansion)* — Salt concentration measurement
- Soil Oxygen Sensor *(future expansion)* — Root-zone oxygen monitoring
- Soil Water Potential Sensor *(future expansion)* — Plant-available water measurement

### Crop Monitoring Sensors

Future versions of the system may include crop-specific monitoring capabilities.

- Leaf Wetness Sensor
- Canopy Temperature Sensor
- PAR (Photosynthetically Active Radiation) Sensor
- Plant Growth Monitoring Sensors

### Power System

The hardware platform is designed to support multiple power configurations.

- USB power supply (development and testing)
- DC adapter power supply
- Rechargeable battery backup *(future expansion)*
- Solar-powered operation *(future expansion)*

### Communication Interfaces

The system uses multiple communication protocols to connect sensors and cloud services.

- Wi-Fi for cloud communication
- I2C for environmental sensors
- OneWire for DS18B20 sensors
- Analog inputs for soil sensors
- UART and SPI for future hardware expansion

### Hardware Expansion

The architecture is designed to support future smart farming features, including:

- Automated irrigation systems
- Water level monitoring
- Pump and valve control
- Greenhouse monitoring
- Livestock environment monitoring
- Multiple distributed sensor nodes
- Edge AI and predictive analytics
- Solar-powered remote deployments

The modular hardware design ensures that additional sensors, communication modules, and automation components can be integrated without significant changes to the core system architecture.

## Technology Stack

The Smart Farm Monitoring System is built using a combination of embedded systems, IoT communication protocols, and cloud-based technologies.

### Hardware
- ESP32 / Arduino microcontroller
- Environmental sensors (temperature, humidity, soil moisture, light, etc.)
- Relay modules (for control systems)
- Power supply unit (solar/adapter-based)

### Firmware / Embedded Software
- C / C++ (Arduino framework)
- Embedded C programming
- Sensor interfacing libraries
- Wi-Fi communication (ESP32 Wi-Fi stack)

### Communication Protocols
- MQTT (lightweight IoT messaging)
- HTTP/REST API (data transmission and integration)
- Wi-Fi (wireless connectivity)

### Backend / Cloud
- Firebase / Node.js backend (optional depending on implementation)
- Cloud database for real-time and historical data storage
- API services for data access

### Frontend / Dashboard
- Web-based dashboard (HTML, CSS, JavaScript)
- Data visualization (charts and graphs)
- Real-time monitoring interface

### Tools & Development Environment
- VS Code (PlatformIO / Arduino IDE)
- Git & GitHub for version control
- Tinkercad / Proteus (circuit simulation)
- Arduino IoT Cloud (optional integration)


## Repository Structure (5-Layer IoT Architecture)

The project follows the PlatformIO standard structure for ESP32 firmware development, ensuring scalability, modularity, and professional embedded system practices.

smart-farm-monitoring-system/
│
├── farmware/                         # 1. Edge Layer (ESP32 Firmware - PlatformIO)
│   ├── platformio.ini
│   ├── src/
│   │   └── main.cpp                 # System entry point
│   │
│   ├── include/
│   │   ├── config.h
│   │   ├── sensors.h
│   │   ├── wifi_manager.h
│   │   └── cloud_client.h
│   │
│   ├── lib/
│   │   ├── Sensors/
│   │   ├── WiFiManager/
│   │   ├── CloudClient/
│   │   └── ControlSystem/          # Relays, actuators (future expansion)
│   │
│   ├── test/
│   ├── data/
│   ├── scripts/
│   └── docs/
│
├── perception/                      # 2. Sensor Layer (Physical world mapping)
│   ├── sensors_list.md             # All sensors used
│   ├── calibration_notes.md        # Sensor calibration data
│   └── hardware_specs.md
│
├── network/                        # 3. Communication Layer
│   ├── mqtt_config.md
│   ├── http_api_docs.md
│   ├── wifi_architecture.md
│   └── protocols_used.md
│
├── cloud/                          # 4. Cloud Layer
│   ├── firebase/
│   ├── api/
│   ├── database_schema.md
│   └── data_processing.md
│
├── intelligence/                   # 5. Intelligence Layer (AI/Analytics)
│   ├── ml_models/
│   ├── forecasting.py
│   ├── data_analysis.py
│   └── insights_engine.md
│
├── dashboard/                      # User Interface Layer (Visualization)
│   ├── index.html
│   ├── style.css
│   ├── app.js
│   └── assets/
│
├── hardware/                      # Physical hardware design
│   ├── schematics/
│   ├── pcb/
│   └── wiring_diagram.png
│
├── docs/                          # System-wide documentation
│   ├── architecture.md
│   ├── system_flow.md
│   ├── api_reference.md
│   └── setup_guide.md
│
├── README.md
├── LICENSE
└── .gitignore


## Quick Start

Follow the steps below to set up and run the Smart Farm Monitoring System on your ESP32 device

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/smart-farm-monitoring-system.git
cd smart-farm-monitoring-system/farmware

### 2. Install PlatformIO

Ensure your development environment is properly set up before proceeding.

#### Requirements
- Install **Visual Studio Code (VS Code)**
- Install **PlatformIO IDE Extension** from the VS Code marketplace

#### Setup Steps
1. Open VS Code
2. Go to Extensions (`Ctrl + Shift + X`)
3. Search for **PlatformIO IDE**
4. Click **Install**
5. Restart VS Code after installation is complete

### 3. Configure the System

Before building and uploading the firmware, you need to configure the system settings according to your environment.

#### Configuration File
Edit the main configuration file located at:

```bash
include/config.h

#### Required Configuration

Update the following parameters in the configuration file:

- Wi-Fi SSID (network name)
- Wi-Fi Password
- Sensor threshold values (e.g., temperature, soil moisture, humidity limits)
- Cloud API or MQTT credentials (if applicable for data transmission)

### 4. Build the Project

Compile the firmware to ensure all dependencies are correctly installed and the code is free from errors.

```bash
pio run

### 5. Upload Firmware to ESP32

Connect your ESP32 device to your computer via USB and upload the compiled firmware.

```bash
pio run --target upload

### 6. Monitor Serial Output

After uploading the firmware, monitor the serial output to verify system behavior and debug in real time.

```bash
pio device monitor

### 7. Verify System Operation

After successful upload and monitoring, confirm that the system is functioning correctly.

#### Checks to Perform

- Sensor readings are displayed correctly on the Serial Monitor
- Wi-Fi connection is successfully established
- Data is being transmitted to the cloud (if enabled)
- Dashboard is receiving and updating real-time data
- No errors or unexpected resets are observed

#### Expected Behavior

- Continuous real-time sensor updates
- Stable network connectivity
- Periodic data logging and transmission
- Proper system initialization on startup


## Sample Output

Below is an example of the expected system output when the Smart Farm Monitoring System is running successfully:

### Serial Monitor Output

```bash
[INFO] Initializing Smart Farm Monitoring System...
[INFO] Connecting to Wi-Fi...
[INFO] Wi-Fi Connected Successfully
[INFO] IP Address: 192.168.1.105

[DATA] Temperature: 26.5 °C
[DATA] Humidity: 62 %
[DATA] Soil Moisture: 48 %
[DATA] Light Intensity: 780 lux

[STATUS] Data sent to cloud successfully
[STATUS] System running normally

### Cloud Data (Example Payload)

The system transmits structured JSON data to the cloud for storage, analysis, and visualization.

```json
{
  "device_id": "farmware-esp32-001",
  "timestamp": "2026-06-10T12:45:30Z",
  "environment": {
    "temperature_c": 26.5,
    "humidity_percent": 62,
    "light_lux": 780
  },
  "soil": {
    "moisture_percent": 48,
    "temperature_c": 24.1
  },
  "status": {
    "wifi": "connected",
    "cloud_sync": "success",
    "system_health": "normal"
  }
}

### System Behavior

When the Smart Farm Monitoring System is running, it operates continuously in a real-time monitoring cycle.

#### Normal Operation Flow

- System initializes and configures all sensors
- ESP32 connects to the configured Wi-Fi network
- Sensor data is collected at fixed intervals
- Data is processed and validated at the edge
- Clean data is transmitted to the cloud
- Dashboard updates in real time

#### Runtime Characteristics

- Continuous monitoring (24/7 operation capability)
- Non-blocking data acquisition cycle
- Automatic recovery from temporary Wi-Fi disconnection
- Stable sensor polling at defined intervals

#### Fault Handling Behavior

- Re-initializes sensors if invalid readings are detected
- Attempts automatic Wi-Fi reconnection on failure
- Skips corrupted readings without stopping the system
- Logs system errors for debugging and maintenance

#### System Output Pattern

- Periodic sensor updates (e.g., every 2–5 seconds)
- Real-time cloud synchronization
- Consistent dashboard updates with minimal latency


## Development Roadmap

The Smart Farm Monitoring System is designed to evolve through structured development phases, from a basic MVP to an advanced intelligent IoT platform.

### Phase 1: MVP Development (Current Stage)
- Basic sensor integration (temperature, humidity, soil moisture, light)
- ESP32 firmware development using PlatformIO
- Real-time data reading and serial monitoring
- Wi-Fi connectivity and basic cloud data transmission
- Simple dashboard for live visualization

### Phase 2: System Stabilization
- Improve sensor calibration and accuracy
- Implement error handling and system fault recovery
- Optimize data transmission efficiency (MQTT/HTTP improvements)
- Enhance firmware modularity and code structure
- Add local data logging (CSV/flash storage)

### Phase 3: Cloud & Dashboard Expansion
- Full cloud database integration (Firebase / custom backend)
- Advanced dashboard with charts and historical data analysis
- User authentication and device management
- Multi-device (multi-farm) support

### Phase 4: Intelligence Layer (AI/ML Integration)
- Weather trend prediction models
- Crop health analysis and recommendations
- Soil condition forecasting
- Smart irrigation decision support system

### Phase 5: Automation & Scaling
- Automated irrigation control system
- Relay-based device control (pumps, fans, lights)
- Mobile application integration
- Deployment for multiple farms (scalable IoT network)

### Future Vision
- Fully autonomous smart farming ecosystem
- AI-driven precision agriculture platform
- Integration with satellite/weather APIs
- Commercial deployment-ready system


## Current Status

The Smart Farm Monitoring System is currently in the **MVP (Minimum Viable Product) development stage**.

### Completed Features
- ESP32 PlatformIO project structure setup
- Basic sensor integration framework
- Real-time data acquisition logic
- Wi-Fi connectivity implementation
- Serial monitoring for debugging
- Modular firmware architecture design
- Initial cloud data structure (JSON payload design)

### In Progress
- Full sensor integration and calibration
- Cloud data transmission (MQTT/HTTP)
- Basic dashboard development
- System testing and stability improvements

### Pending Development
- Historical data storage and visualization
- Alert and notification system
- Advanced analytics and insights layer
- Automation features (relay control, irrigation logic)

### Overall System State
- Firmware: Functional prototype stage
- Hardware: Partially integrated
- Cloud: Under development
- Dashboard: Early development stage


## Future Versions

The Smart Farm Monitoring System is designed for continuous improvement and expansion into a full-scale smart agriculture platform.

### Version 1.0 (MVP Release)
- Stable ESP32 firmware with core sensor integration
- Real-time data monitoring via serial and cloud
- Basic dashboard for live visualization
- Wi-Fi based data transmission

### Version 2.0 (Stability & Optimization)
- Improved sensor accuracy and calibration system
- MQTT-based lightweight communication protocol
- Local data caching during network downtime
- Enhanced error handling and system reliability

### Version 3.0 (Full Cloud Integration)
- Advanced cloud database structure
- Historical data storage and retrieval
- Interactive dashboard with analytics and trends
- Multi-device support (multiple farm nodes)

### Version 4.0 (Intelligence Layer)
- Machine learning-based weather forecasting
- Crop health prediction models
- Soil condition analysis and recommendations
- Smart decision support system for farmers

### Version 5.0 (Automation & Scale)
- Automated irrigation and control systems
- Relay-based actuator integration
- Mobile application support
- Scalable deployment across multiple farms

### Long-Term Vision
- Fully autonomous precision agriculture system
- AI-driven farm management platform
- Integration with satellite and weather APIs
- Commercial-grade IoT agriculture ecosystem
## System Architecture


## Author

**Ezra Keumbu Asiago**

- Location: Kitale, Kenya  
- Role: Electrical & Electronics Engineer | Embedded Systems Developer  
- Education: Diploma in Electrical and Electronics Engineering (Railways Training Institute)  
- Skills: Embedded C, Arduino, ESP32, IoT Systems, AutoCAD, Electrical Installation, Circuit Design  

### Contact

- Email: keumbuasiago@gmail.com  
- Phone: 0707559463  
- LinkedIn: [Add your LinkedIn profile link here]


### Project Note

This project is currently under active development as a personal learning and portfolio initiative in **IoT-based smart agriculture systems**, focused on real-time environmental monitoring, cloud integration, and data-driven farming solutions.


## License

This project is currently under active private development and is intended for learning and portfolio purposes.
