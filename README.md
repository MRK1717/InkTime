InkTime Smartwatch – Hardware Design Project

Overview
InkTime is an open-source smartwatch designed to be low-cost, energy-efficient, and suitable for mass production.
This project focuses on the complete hardware design of the device, from system specifications to a fully functional PCB and mechanical integration.

The system integrates a microcontroller, an e-paper display, motion sensing, power management, and user interaction modules into a compact wearable device.

System Architecture
The smartwatch is built around the following functional blocks:

1. Microcontroller Unit (MCU) – Nordic nRF52840
2. Display Module – E-Paper display
3. Sensor Module – IMU (motion sensor)
4. Power Management – LiPo battery and charging circuit
5. User Interface – Tactile buttons
6. Connectivity and Debug – USB-C and SWD

Hardware Description

Microcontroller (nRF52840)
The core of the system is the nRF52840, a low-power SoC with integrated BLE capabilities.

Supply:

1. 3.3V regulated supply
2. Internal voltage regulator

Interfaces used:

1. SPI → E-paper display
2. I2C → IMU sensor
3. GPIO → Buttons
4. SWD → Debugging

Decoupling capacitors of 100nF are placed close to power pins for stability.

Display System (E-Paper)
The smartwatch uses an e-paper display for low power consumption.

1. Interface: SPI
2. Signals: MOSI, SCK, CS, DC, RST
3. Powered from 3.3V rail

All display-related signals are routed carefully to minimize noise and interference.

Motion Sensor (IMU)
The IMU provides motion detection.

1. Interface: I2C
2. Signals: SDA, SCL
3. Includes pull-up resistors and decoupling capacitor

Placed away from noisy power areas.

Power Management

USB-C Input

1. Provides VBUS (5V)
2. Used for charging and powering the system

Battery Charging Circuit

1. Charges Li-Po battery from USB
2. Includes filtering capacitors
3. Positioned close to USB input

Battery (Li-Po)

1. Connected via test pads
2. Provides VBAT

Voltage Regulation

1. System powered at 3.3V
2. Stable supply distributed across PCB

User Input (Buttons)
Three tactile buttons are used for user interaction.

1. Connected via GPIO
2. Used for navigation and control

Debug Interface

1. SWD interface using SWDIO and SWDCLK
2. Test pads available for debugging

Pin Usage (nRF52840)

Function | Interface | Description
E-Paper | SPI | Display control
IMU | I2C | Motion sensing
Buttons | GPIO | User input
Debug | SWD | Programming and debugging
Power | VDD and VREG | Supply

PCB Design Considerations

1. 2-layer PCB with ground planes
2. Power traces minimum 0.3 mm
3. Signal traces minimum 0.15 mm
4. No 90 degree routing angles
5. Minimal vias on power lines
6. Decoupling capacitors placed close to IC pins
7. Via stitching applied between ground planes

RF and Antenna

1. Antenna placed at PCB edge
2. No copper under antenna
3. No routing in antenna keepout area

Mechanical Design

The device includes:

1. PCB with all components
2. LiPo battery
3. E-paper display
4. Enclosure

A full 3D assembly was created, including an exploded view.

Manufacturing Outputs

Available in folder Manufacturing:

1. Gerber files
2. Bill of Materials
3. Pick and Place file

Design Files Structure

1. Hardware – schematic and PCB files
2. Manufacturing – fabrication files
3. Mechanical – 3D models
4. Images – PCB renders and diagrams

Design Notes

1. Routing optimized for compact layout
2. Power distribution carefully handled
3. Minor constraints accepted due to limited space
4. Design verified using ERC and DRC

Conclusion
The InkTime smartwatch hardware design integrates all required subsystems into a compact and manufacturable PCB.

The design respects electrical, mechanical, and RF constraints and is ready for validation and production.

License
This project is released under an open-source license.
