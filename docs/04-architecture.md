# 04 - System Architecture

## Overview

The architecture of the Smart Farm Monitoring System is designed to enable the efficient collection, processing, transmission, storage, visualization, and utilization of agricultural data. The system follows a layered IoT architecture that separates sensing, processing, communication, cloud services, and user applications into distinct functional components.

This layered approach improves scalability, maintainability, reliability, and future extensibility while supporting real-time agricultural monitoring and decision-making.


## High-Level System Architecture

Sensors → ESP32 → Wi-Fi → Cloud Platform → Dashboard → Decisions


The architecture transforms physical farm conditions into actionable information through a structured flow of data.


## Architectural Layers

The Smart Farm Monitoring System consists of four primary layers:

### 1. Edge Layer

The Edge Layer is responsible for acquiring data from the physical farm environment and performing local processing operations before transmission.

#### Components

##### Sensors

Environmental Sensors:

- Air temperature sensor
- Relative humidity sensor
- Rainfall sensor
- Light intensity sensor

Soil Sensors:

- Soil moisture sensor
- Soil temperature sensor
- Soil pH sensor (future expansion)
- Electrical conductivity sensor (future expansion)

Crop Monitoring Sensors:

- Canopy temperature sensor (future expansion)
- Growth monitoring sensors (future expansion)

##### ESP32 Microcontroller

The ESP32 acts as the central edge computing device.

Responsibilities include:

- Reading sensor data
- Filtering and validating measurements
- Converting raw sensor values into engineering units
- Managing communication processes
- Coordinating system operations

#### Edge Layer Functions

- Data acquisition
- Local processing
- Sensor management
- Device control
- Data preparation for transmission


### 2. Communication Layer

The Communication Layer enables the transfer of data between the edge device and cloud services.

#### Communication Technologies

Current Implementation:

- Wi-Fi

Future Expansion:

- MQTT
- LoRaWAN
- Cellular connectivity

#### Data Transmission Process

The ESP32 packages sensor readings into structured data formats and transmits them securely to cloud platforms.

Example:

  json
{
  "temperature": 28.5,
  "humidity": 65,
  "soil_moisture": 42,
  "light_intensity": 780
}


#### Communication Layer Functions

- Data transmission
- Device connectivity
- Network management
- Remote communication
- Data synchronization


### 3. Cloud Layer

The Cloud Layer serves as the centralized platform for data storage, processing, and management.

#### Potential Cloud Platforms

- Firebase
- AWS IoT
- ThingsBoard

#### Cloud Services

The cloud infrastructure is responsible for:

- Data storage
- Historical data management
- Analytics processing
- Device management
- Remote accessibility

#### Benefits of Cloud Integration

- Centralized data storage
- Scalability
- Remote monitoring
- Data backup and recovery
- Advanced analytics capabilities


### 4. Application Layer

The Application Layer provides interfaces through which users interact with the system.

#### Components

##### Dashboard

Provides:

- Real-time sensor monitoring
- Historical data visualization
- Charts and graphs
- Farm performance metrics

##### Alert System

Provides notifications when:

- Soil moisture falls below thresholds
- Temperature exceeds acceptable limits
- Sensor failures occur

##### Future Applications

- Mobile applications
- Automated control systems
- Machine learning analytics
- Predictive agriculture tools

#### Application Layer Functions

- Data visualization
- Reporting
- User interaction
- Decision support
- Farm management


## Data Flow Through the System

The Smart Farm Monitoring System follows a continuous data processing pipeline.

### Step 1: Environmental Data Collection

Sensors deployed throughout the farm measure environmental and soil conditions.

### Step 2: Edge Processing

The ESP32 collects and processes sensor data locally.

### Step 3: Data Transmission

Processed data is transmitted through Wi-Fi networks to cloud services.

### Step 4: Cloud Processing

The cloud stores, organizes, and analyzes incoming data.

### Step 5: Visualization

Dashboards display information in an understandable format.

### Step 6: Decision Support

Farmers use generated insights to make informed management decisions.


## Decision-Making Framework

The ultimate objective of the architecture is to support agricultural decision-making.

Examples include:

### Irrigation Management

- Identify dry soil conditions
- Optimize irrigation schedules
- Reduce water wastage

### Environmental Monitoring

- Detect temperature fluctuations
- Monitor humidity levels
- Track rainfall events

### Resource Optimization

- Improve fertilizer application
- Reduce operational costs
- Increase productivity

### Risk Management

- Detect abnormal conditions early
- Generate alerts and notifications
- Reduce crop losses


## Architectural Benefits

The proposed architecture provides several advantages:

### Scalability

New sensors and services can be added without redesigning the system.

### Modularity

Each layer operates independently while remaining integrated with the overall system.

### Reliability

Distributed processing improves system robustness.

### Maintainability

Individual components can be upgraded or replaced independently.

### Future Readiness

The architecture supports future integration of:

- Precision agriculture technologies
- Artificial intelligence systems
- Predictive analytics
- Automated irrigation systems


## Conclusion

The Smart Farm Monitoring System architecture provides a structured framework for transforming raw environmental data into actionable agricultural intelligence. Through the integration of edge computing, wireless communication, cloud services, and user-facing applications, the system establishes a scalable and efficient platform for modern data-driven agriculture.

This architecture serves as the foundation upon which future automation, analytics, and precision agriculture capabilities can be built.
