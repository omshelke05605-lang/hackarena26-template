# ZoneCast – Smart Emergency Announcement System

VICSTA Hackathon – Grand Finale
VIT College, Kondhwa Campus | 5–6 March

---

## Team Details

**Team Name:** Team Endeavor

**Members:**
Atharva Bhagwat
Om Shelke
Parth Bujade
Payal Kainge

**Domain:** IoT and Smart Infrastructure

---

## Problem Statement

In large buildings such as colleges, malls, hospitals, and office complexes, emergency communication usually relies on sirens or alarms. These systems are often ineffective because they do not provide clear instructions and can create confusion during critical situations.

Traditional alarm systems broadcast the same signal across the entire building. However, in many situations different areas require different instructions. People need clear and zone-specific guidance to evacuate safely and efficiently.

---

## Proposed Solution

ZoneCast is an IoT-based emergency communication system designed to send real-time alerts to specific zones within a building.

Instead of relying only on a siren, the system provides both text and voice announcements. Each zone in the building is connected to an ESP32-based device that receives messages from a central dashboard. When an alert is triggered, only the relevant zones receive the instructions.

This approach helps reduce panic and ensures that people receive clear information about what action they should take.

---

## System Architecture

```
Admin Dashboard
       |
       |  MQTT Alert Message
       v
   MQTT Broker
       |
       |
   ESP32 Device  --> Zone A Speaker / Display
       |
   ESP32 Device  --> Zone B Speaker / Display
       |
   ESP32 Device  --> Zone C Speaker / Display
```

### Working Flow

1. The administrator sends an alert through the dashboard.
2. The alert message is published to an MQTT broker.
3. ESP32 devices subscribe to topics corresponding to their zones.
4. The appropriate devices receive the message instantly.
5. The message is displayed or announced through the connected hardware.

---

## Technologies Used

### Hardware

* ESP32 Microcontroller
* OLED Display
* Speaker or Buzzer
* WiFi Network

### Software

* MQTT Communication Protocol
* Python (for MQTT testing and simulation)
* HTML-based dashboard interface
* Arduino IDE for firmware development

---

## Project Structure

```
hackarena26-template
│
├── firmware
│   ├── zonecast_firmware_basic.ino
│   ├── zonecast_nexus_firmware.ino
│   ├── i2c_scanner.ino
│   └── hardware_test.ino
│
├── dashboard
│   ├── zonecast_dashboard_basic.html
│   └── zonecast_nexus_dashboard.html
│
├── backend
│   ├── mqtt_simulator.py
│   └── mqtt_test.py
│
├── docs
│   └── ZoneCast_Beginners_Guide.docx
│
└── README.md
```

---

## How to Run the Project

Follow the steps below to set up and run the ZoneCast system.

### 1. Clone the Repository

```
git clone https://github.com/Atharva1305/hackarena26-template.git
cd hackarena26-template
```

---

### 2. Install Required Software

Ensure that the following tools are installed on your system:

* Arduino IDE
* Python 3
* ESP32 board support package for Arduino

---

### 3. Install ESP32 Board in Arduino IDE

1. Open Arduino IDE.
2. Navigate to **File → Preferences**.
3. In "Additional Boards Manager URLs", add the following link:

```
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
```

4. Open **Tools → Board Manager**.
5. Install **ESP32 by Espressif Systems**.

---

### 4. Upload Firmware to ESP32

Open one of the firmware files using Arduino IDE:

```
firmware/zonecast_firmware_basic.ino
```

or

```
firmware/zonecast_nexus_firmware.ino
```

Update the following parameters in the code before uploading:

```
WiFi SSID
WiFi Password
MQTT Broker Address
Zone ID
```

After updating the configuration:

1. Connect the ESP32 board via USB.
2. Select **ESP32 Dev Module** from the board menu.
3. Upload the firmware.

---

### 5. Install Python Dependencies

Install the MQTT library for Python:

```
pip install paho-mqtt
```

---

### 6. Run MQTT Simulator

To simulate or test message communication, run:

```
python mqtt_simulator.py
```

For additional testing:

```
python mqtt_test.py
```

---

### 7. Launch the Dashboard

Open the dashboard file in a web browser:

```
dashboard/zonecast_dashboard_basic.html
```

or

```
dashboard/zonecast_nexus_dashboard.html
```

From the dashboard, alerts can be sent to specific zones connected to the system.

---

## Key Features

* Zone-based emergency communication
* Real-time message delivery using MQTT
* Combination of voice and text alerts
* Centralized control through a web dashboard
* Scalable design suitable for large buildings

---

## Testing Tools

The following utilities are included for development and debugging:

* MQTT simulator scripts
* MQTT testing scripts
* I2C scanner for checking hardware connections

---

## Future Improvements

Possible extensions of the system include:

* Integration with a mobile application
* AI-based emergency detection
* Integration with building fire alarm systems
* Deployment across multiple buildings or campuses

---

## Attribution

This project uses open-source tools and libraries including:

* ESP32 Arduino libraries
* MQTT communication libraries
* Standard web technologies for the dashboard

---

## Built During

VICSTA Hackathon Grand Finale
VIT Pune – Kondhwa Campus

---

"The world is not enough — but it is such a perfect place to start."
— James Bond
