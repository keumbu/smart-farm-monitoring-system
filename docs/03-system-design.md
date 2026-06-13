# 03 - System Design

## Overview

The Smart Farm Monitoring System is an Internet of Things (IoT)-based agricultural monitoring platform designed to enable real-time acquisition, processing, transmission, and visualization of environmental and soil data. The system integrates distributed sensing units, an ESP32 microcontroller, wireless communication protocols, cloud computing infrastructure, and data visualization interfaces to support data-driven agricultural decision-making.

The primary objective of the system is to modernize traditional agricultural practices by introducing continuous environmental monitoring and enabling intelligent, evidence-based farm management through IoT technologies.


## 3.1 System Requirements

### Functional Requirements

The system shall:

- Continuously acquire environmental and soil parameters from deployed sensors  
- Perform real-time data processing using an embedded edge device (ESP32)  
- Transmit sensor data to cloud platforms via wireless communication  
- Store and visualize agricultural data for monitoring and analysis  
- Support remote access to farm environmental conditions  

### Non-Functional Requirements

The system shall ensure:

- Low-latency communication (< 2 seconds under stable network conditions)  
- Reliable and continuous data acquisition  
- Energy-efficient operation suitable for field deployment  
- Scalability to support additional sensors and system expansion  
- Maintainability of firmware and system architecture  


## 3.2 System Architecture

The Smart Farm Monitoring System is designed using a layered IoT architecture model consisting of sensing, edge processing, communication, cloud, and application layers.

Sensors → ESP32 (Edge Layer) → Wireless Communication → Cloud Platform → Visualization Dashboard → End User


### 3.2.1 Sensing Layer

The sensing layer is responsible for capturing environmental and soil parameters relevant to agricultural monitoring. The system incorporates:

- Temperature sensors  
- Humidity sensors  
- Soil moisture sensors  
- Light intensity sensors  
- Future extensions: rainfall, CO₂ concentration, soil pH sensors  


### 3.2.2 Edge Processing Layer

The ESP32 microcontroller serves as the edge computing unit responsible for:

- Acquiring data from multiple sensors  
- Performing local preprocessing and filtering  
- Managing communication with cloud services  
- Coordinating system timing and sampling intervals  


### 3.2.3 Communication Layer

Data transmission between the edge device and cloud infrastructure is achieved using:

- Wi-Fi (primary communication protocol)  
- HTTP/HTTPS protocols for data transfer  
- MQTT protocol (planned for lightweight IoT messaging optimization)  


### 3.2.4 Cloud Layer

The cloud layer provides centralized data management and processing capabilities, including:

- Data storage and persistence  
- Historical data analysis  
- Remote accessibility  
- Integration with visualization dashboards  

Potential platforms include Firebase, AWS IoT, and ThingsBoard.


### 3.2.5 Application Layer

The application layer provides user-facing interfaces for:

- Real-time monitoring dashboards  
- Data visualization and analytics  
- Alert and notification systems  
- Future mobile application integration  


## 3.3 System Data Flow

The system follows a structured IoT data pipeline from sensing to decision support:

Environmental Sensors → ESP32 → Data Processing → Wireless Transmission → Cloud Storage → Dashboard Visualization



### Data Representation

Sensor data is transmitted in a lightweight structured format such as JSON:

   json
{
  "temperature": 28.5,
  "humidity": 65,
  "soilMoisture": 40,
  "lightIntensity": 720
}


## 3.3 Sampling Characteristics

The system operates under defined sensing and communication parameters to ensure consistency in data acquisition and transmission.

- **Sensor Sampling Interval:** 5–30 seconds (configurable depending on application requirements)  
- **Transmission Mode:** Real-time streaming or buffered batch transmission depending on network stability  
- **Data Format:** Lightweight IoT-compatible structured payload (e.g., JSON format) optimized for low bandwidth communication  


## 3.4 Selection of ESP32 Microcontroller

The ESP32 microcontroller is selected as the core edge processing unit due to its suitability for IoT-based embedded systems, offering a balance between performance, power efficiency, and integrated wireless communication capabilities.

### Key Technical Advantages

#### Integrated Wireless Connectivity
The ESP32 features built-in Wi-Fi capability, enabling direct communication with cloud platforms without the need for external communication modules. This significantly reduces system complexity and cost.

#### High Processing Capability
The dual-core architecture supports concurrent execution of multiple tasks such as sensor data acquisition, local data processing, and wireless communication management, making it suitable for real-time IoT applications.

#### Extensive Peripheral Support
The microcontroller provides multiple hardware interfaces for sensor and module integration, including:

- General Purpose Input/Output (GPIO)  
- Analog-to-Digital Converter (ADC)  
- Inter-Integrated Circuit (I2C)  
- Serial Peripheral Interface (SPI)  
- Universal Asynchronous Receiver-Transmitter (UART)  

#### Low Power Consumption
The ESP32 supports multiple power management modes, including deep sleep functionality, making it suitable for battery-powered and solar-powered agricultural deployments.

#### Development Ecosystem
The ESP32 is supported by a mature and widely adopted development ecosystem, including:

- Arduino Framework  
- PlatformIO  
- ESP-IDF (Espressif IoT Development Framework)  

This ecosystem accelerates development and enhances system maintainability.


## 3.5 Design Philosophy

The Smart Farm Monitoring System is designed based on fundamental engineering principles to ensure robustness and scalability:

- **Modularity:** Each subsystem operates independently and can be upgraded without affecting the overall system  
- **Scalability:** The architecture supports future expansion of sensors, devices, and cloud services  
- **Reliability:** The system ensures consistent and stable data acquisition and transmission  
- **Maintainability:** Structured firmware and system architecture support long-term updates and debugging  
- **Cost-effectiveness:** The design prioritizes low-cost components suitable for real-world agricultural deployment  


## 3.6 System Constraints

The system operates under the following technical and environmental constraints:

- Dependence on stable Wi-Fi connectivity for cloud communication  
- Sensor accuracy limitations determined by hardware specifications  
- Power constraints in remote or off-grid agricultural environments  
- Network latency variability in rural deployment scenarios  
- Limited computational resources compared to advanced edge AI systems  


## 3.7 Summary

The Smart Farm Monitoring System presents a scalable IoT-based architecture for real-time agricultural monitoring. By integrating environmental sensing devices, ESP32-based edge processing, wireless communication technologies, cloud computing infrastructure, and visualization tools, the system enables efficient and data-driven agricultural management.

Furthermore, the architecture establishes a strong foundation for future enhancements, including automated irrigation systems, predictive analytics, artificial intelligence integration, and precision agriculture applications.
