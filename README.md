# InkTime Smartwatch PCB

## General Description

This project involves the development of a PCB for an open-source smartwatch named InkTime, based on the nRF52840 microcontroller. The primary goal was to integrate all necessary components, including processing, sensors, power management, and user interface, onto a compact board that adheres to both electrical constraints and the mechanical limitations of the device housing.

The design was created using Fusion 360 Electronics, following the provided electrical schematics and laboratory layout guidelines. Significant emphasis was placed on precise routing, ground plane integrity, and component density within a limited footprint.

## Hardware Components

The system's core components include:

    - nRF52840: Main microcontroller with BLE capabilities.

    - IMU: Accelerometer and Gyroscope for motion tracking.

    - E-Paper Display: Ultra-low-power visual interface.

    - PMIC: Power Management IC for system stability.

    - Li-Po Battery: System power source.

    - USB-C: Interface for charging and power supply.

    - Haptic Motor: Vibration feedback.

Component Connectivity:

    - IMU: Connected to the MCU via I2C (SDA, SCL).

    - Display: Connected via SPI (MOSI, SCK, CS, DC, RST).

    - PMIC: Manages the entire system's power distribution.

    - USB-C: Connected directly to the charging circuitry.

    - Haptic Motor: Controlled via standard GPIO.

## Hardware Functionality

The system is centered around the nRF52840, which manages all peripherals and communications. Communication with sensors and the display is handled through standard interfaces:

    - SPI: Utilized for the display to ensure higher data transfer speeds.

    - I2C: Utilized for the IMU for simple and efficient sensor polling.

The system is powered by a Li-Po battery via a PMIC circuit that provides:

    - Voltage stabilization.

    - Overcharge/discharge protection.

    - Power distribution across all subsystems.

USB-C serves a dual purpose for battery charging and direct system power. The haptic motor provides tactile feedback and is managed by a dedicated GPIO pin.

### Estimated Consumption:

    - MCU: Low consumption in sleep mode, higher during active BLE transmission.

    - E-Paper Display: Negligible consumption (only draws power during screen updates).

    - IMU: Low power consumption over I2C.

## PCB Layout

### The PCB was designed using a 2-layer stackup:

    - Top Layer: Primary component placement and signal routing.

    - Bottom Layer: Supplementary routing and dedicated ground plane.

### Design Rules Applied:

    - Power Traces: Increased width for power lines (e.g., 3V3, VBUS).

    - Signal Traces: Minimum width of 0.15 mm.

    - Geometry: Avoided 90-degree angles to prevent signal reflection and manufacturing issues.

### Antenna Design:

    - Copper-free zone maintained directly beneath the antenna.

    - No routing allowed in the antenna keepout area to ensure signal integrity.
