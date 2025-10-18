# PCB - Domestic Vibration Sensor
This is a compact PCB design for a home and industrial vibration detection system, capable of capturing precise motion and vibration data using a 6-axis IMU sensor and an ESP32-based microcontroller. Features:

1. 🌀 Motion & vibration detection using the MPU-6050 (3-axis accelerometer + 3-axis gyroscope)
2. 📶 Wi-Fi and Bluetooth connectivity via Arduino Nano ESP32
3. 🔋 Battery-powered operation from a 7.4 V Li-ion/LiPo pack with onboard 3.3 V regulation
4. 🔘 Hardware reset button with RC filter for stable system control
5. 💤 Low-power operation modes for extended battery life
6. 🏠 Ideal for smart home systems, appliance monitoring, and vibration analytics

# Usage
To use the Domestic Vibration Sensor, follow these steps:

1. Connect a 7.4 V Li-ion/LiPo battery to the power input terminal.
2. Mount the PCB on the surface or object you wish to monitor (e.g., washing machine, air conditioner, motor).
3. Power on the system and connect via Wi-Fi or Bluetooth.
4. Access vibration data in real-time or log readings locally for later analysis.
5. Configure motion thresholds and alerts based on application needs.
6. The ESP32 automatically manages power and sensor interrupts for efficient operation.
7. The device can monitor subtle vibration patterns, detect abnormal activity, and send alerts or logs to a connected interface, making it perfect for home automation, predictive maintenance, and IoT condition monitoring.

# Getting Started
To get started with the Domestic Vibration Sensor PCB design:

1. Clone this repository to your local environment.
2. Open the KiCad project files to review schematic and layout.
3. Verify critical sections:
4. I²C routing between MPU-6050 and ESP32
5. Proper power regulation and decoupling
6. Placement of interrupt and reset lines
7. Send the Gerber files to PCBWay or your preferred PCB manufacturer.
8. Once the PCB is fabricated, solder the following components in order:
  - Power regulation stage
  - Arduino Nano ESP32 header pins
  - MPU-6050 sensor
  - Passive components and terminal connectors
  - Upload your firmware using the Arduino IDE or ESP-IDF.
  - Connect your battery and test vibration readings via serial monitor or wireless dashboard

# Contributing
If you would like to contribute to the Domestic Vibration Sensor project, please follow these steps:

1. Fork this repository.
2. Create a feature branch (git checkout -b feature/improvement).
3. Implement and document your enhancements.
4. Submit a pull request with clear details about your improvements.

# Areas for Contribution
1. 🔋 Power optimization and sleep management
2. 📡 Wireless data transmission and logging
3. 🧭 Sensor calibration and digital filtering
4. 🏠 Enclosure and mechanical mounting designs
5. 📊 Data visualization interfaces and dashboards
6. 🔧 PCB layout and EMI/ESD improvements

# License
This Domestic Vibration Sensor PCB design is licensed under the MIT License. See the [MIT License ↗](https://opensource.org/license/mit/) file for more information.
