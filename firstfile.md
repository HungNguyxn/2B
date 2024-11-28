# DIY Syringe Pump

## Introduction

Welcome to our DIY Syringe Pump project! This project utilizes the ESP32 Wroom 3 microcontroller to control a stepper motor, allowing for precise control of fluid delivery in various applications. Our syringe pump is designed to be user-friendly and can be adapted for different types of syringes, making it suitable for both educational and practical uses in laboratories or home settings.

## Project Overview

The syringe pump is controlled via an intuitive interface, and it can be programmed to deliver specific volumes of liquid at desired rates. This project demonstrates the integration of hardware and software, showcasing our skills in electronics, programming, and system design.

## Electronic Components

| Component             | Description                      |
|-----------------------|----------------------------------|
| Stepper Motor         | NEMA 17                          |
| Microcontroller       | ESP32 Wroom 3                   |
| Power Source          | 12V DC                           |
| Voltage Regulator     | LM2596                           |
| Control Driver        | TMC2209                          |
| User Interface        | 4 Push Buttons                   |
| Display               | LCD I2C 16x2                    |

## Mechanical Components

| Purpose            | Product Information                                   | Vendor         | Cost (VND) | Note                  |
|--------------------|------------------------------------------------------|----------------|------------|-----------------------|
| Frame              | Aluminum Extrusion Profile 20x20mm                   | Thegioiic      | 150,000    | 1 meter length        |
| Linear Motion      | Pad Screw T8 (1) Thread Step 2mm, Length 40cm With Nut (2) | Thegioiic      | 63,000     | For linear movement    |
| Coupling           | Stepper Motor Coupling 5mm to 8mm                     | Tmshop         | 25,000     | Connects motor to lead screw |
| Syringe Holder     | Custom 3D-printed Syringe Holder                      | Local Vendor    | 30,000     | Designed for 20ml syringes |
| Base               | Acrylic Base Plate 5mm Thickness                      | Local Vendor    | 50,000     | Provides stability      |

## Diagrams

+------------------+
        |                  |
        |       12V DC    |
        |                  |
        +---------+--------+
                  |
                  |
                  v
        +---------+--------+
        |                  |
        |      LM2596     |
        |                  |
        +---------+--------+
                  |
                  |
                  v
        +---------+--------+
        |                  |
        |      ESP32      |
        |                  |
        +---------+--------+
          /        |       \
         /         |        \
        v          v         v
+-------+-------+  +---------+---------+
| 4 Push Buttons |  |      LCD I2C     |
|                |  |       16x2      |
+----------------+  +------------------+
         |
         v
+---------------------+
|     TMC2209 Driver  |
+---------------------+
         |
         v
+---------------------+
|     NEMA 17 Motor   |
+---------------------+

### Flow Chart

```mermaid
graph TD;
    A[Start] --> B{User Input}
    B -->|Set Volume| C[Set Volume to Pump]
    B -->|Set Rate| D[Set Delivery Rate]
    C --> E[Initialize Pump]
    D --> E
    E --> F{Start Pumping}
    F -->|Yes| G[Deliver Liquid]
    G --> H{Is Delivery Complete?}
    H -->|Yes| I[Stop Pump]
    H -->|No| G
    I --> J[End]


