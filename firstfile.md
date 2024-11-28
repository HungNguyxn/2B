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

 Diagrams

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

#### Block diagram

graph TD;
    A[User Interface] --> B[Microcontroller (ESP32)]
    B --> C[Control Driver (TMC2209)]
    C --> D[Stepper Motor (NEMA 17)]
    B --> E[Display (LCD I2C 16x2)]
    B --> F[Push Buttons]
    B --> G[Power Source (12V DC)]
    G --> H[Voltage Regulator (LM2596)]