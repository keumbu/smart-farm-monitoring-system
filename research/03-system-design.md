# System Design  
## Smart Farm Monitoring System (MVP – Mark 1)


## 1. System Overview

The Smart Farm Monitoring System is an IoT-based embedded system designed to collect environmental and soil data using sensors, process the data using an ESP32 microcontroller, and support future cloud-based monitoring and automation.

The system follows a modular architecture consisting of three main layers:

- Sensor Layer
- Processing Layer
- Application Layer


## 2. System Architecture

### High-Level Architecture

Sensor Layer → ESP32 Processing Unit → Serial Monitor / Cloud (Future)


## 3. Sensor Layer

This layer is responsible for collecting real-world environmental data.

### Components:

- **Soil Moisture Sensor**
  - Measures water content in soil
  - Provides analog signal to ESP32

- **DHT22 Sensor**
  - Measures temperature and humidity
  - Provides digital signal to ESP32


## 4. Processing Layer (ESP32)

The ESP32 microcontroller acts as the central processing unit.

### Responsibilities:

- Reads sensor data (analog + digital)
- Processes raw sensor values
- Applies threshold logic (future automation)
- Sends data to output interfaces
- Handles WiFi communication (future expansion)

### Key Features:

- Dual-core 32-bit processor
- Built-in WiFi and Bluetooth
- Supports Arduino framework (PlatformIO)


## 5. Application Layer

This layer defines how data is presented and used.

### MVP Stage:

- Serial Monitor output via USB

### Future Stage:

- Web dashboard (real-time monitoring)
- Mobile application interface
- Cloud storage and analytics


## 6. Data Flow Diagram

Sensor Layer  
↓  
ESP32 Microcontroller  
↓  
Data Processing & Formatting  
↓  
Serial Monitor (MVP)  
↓  
Future: WiFi → Cloud Dashboard → Mobile App


## 7. ESP32 Pin Mapping (Initial Design)

### Soil Moisture Sensor
- Analog Output → GPIO 34

### DHT22 Sensor
- Data Pin → GPIO 4

### Relay Module (Future Use)
- Control Pin → GPIO 26


## 8. Communication Design

### MVP Stage:
- USB Serial Communication (115200 baud rate)

### Future Stage:
- WiFi (HTTP / MQTT protocols)
- Cloud IoT platforms (Arduino IoT Cloud / Firebase)


## 9. Power Design

### Options:
- USB 5V power (development stage)
- 5V regulated supply (deployment stage)
- Solar power system (future enhancement)


## 10. System Constraints

- Sensor accuracy may vary with environmental conditions
- ESP32 ADC limitations may affect soil moisture precision
- Initial system does not include real-time cloud integration
- Requires stable power for continuous operation


## 11. Future System Expansion

The architecture is designed to support:

- Automated irrigation system using relays
- Multi-sensor farm network (multiple ESP32 nodes)
- Cloud-based analytics and dashboards
- Machine learning-based irrigation prediction
- Mobile app notifications and alerts


## 12. Conclusion

This system design defines the complete architecture of the Smart Farm Monitoring System. It provides a clear transition from a basic MVP (serial monitoring) to a full IoT-enabled smart agriculture platform with cloud integration and automation capabilities.