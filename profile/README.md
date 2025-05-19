# Team A#

Capstone Design 2025 Fall to 2025 Spring

Department of Embedded System Engineering

Incheon National University

# Intention-Aware Mobility Device Using Fixed-Handle Pressure Sensor Input

This project presents the design and implementation of a semi-autonomous mobility aid device that recognizes the user's walking intention using a fixed-handle pressure sensor. It was developed as part of a capstone design project in the Department of Embedded Systems Engineering at Incheon National University.

## Overview

The proposed system aims to support the elderly and people with walking difficulties by providing intuitive control through pressure applied to a fixed handle. Unlike traditional manual walkers or powered ride-on devices, this system seeks to balance cost-efficiency, safety, and autonomy.

## Motivation

- Manual walkers require physical force, posing safety risks especially on slopes.
- Powered devices reduce physical burden but are expensive, bulky, and reduce physical activity.
- This system offers an in-between solution: a cost-effective, semi-autonomous device that promotes active walking with intuitive control.

## System Architecture

The device integrates the following components:

- **FSR Array Sensors (Fixed Handle):** Detects the user's grip pressure to infer walking intentions (forward, backward, turn).
- **Gyroscope (MPU-9250):** Measures slope angle to adjust motor output on inclined surfaces.
- **Hall Effect Sensors:** Measures wheel speed using custom-built encoders with neodymium magnets.
- **MCU (Arduino Nano):** Handles real-time sensor input and motor control via PWM.
- **SBC (Raspberry Pi 5):** Performs high-level processing and communicates with MCU over USB using JSON-formatted serial data.

## Hardware Design

- Two cylindrical FSR sensor arrays (16x16 each) are mounted on a PVC pipe used as the handle.
- Dual DC motors with gearboxes are mounted on the rear wheels of a modified walker.
- Hall sensors detect wheel rotation for speed calculation.
- 12V 18Ah lead-acid battery powers the motors and electronics.

## Software Flow

- MCU reads sensor data and sends it to the SBC.
- SBC parses the data in Python and calculates the target wheel speeds based on pressure distribution and terrain slope.
- Final PWM commands are sent back to the MCU to control motor drivers.

## Evaluation

A user test was conducted with 5 participants aged in their 50s and 60s. Test scenarios included:

- Forward and backward movement
- Uphill and downhill slopes
- Emergency stops

**User satisfaction survey results (out of 5.0):**

- Forward stability and speed control: 4.8  
- Downhill safety and control: 5.0  
- Braking reliability: 5.0  
- Overall ease of use and safety: 4.6+

## Conclusion

This project demonstrates a practical and scalable approach to mobility assistance for the elderly and physically challenged. The intuitive sensor-based control and simple architecture make it suitable for both personal and industrial use (e.g., logistics carts). Future work may include machine learning-based intent recognition and integration with vision systems.