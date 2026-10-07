# Smart Thermostat System

A Raspberry Pi–based embedded systems project that uses Python, state machines, sensors, GPIO controls, and serial communication to create a functioning smart thermostat prototype.

## About the Project

This repository contains two embedded systems projects developed while exploring hardware and software integration: a Morse Code state machine and a Smart Thermostat System.

The Morse Code project uses a Raspberry Pi, LEDs, a button, and an LCD display to transmit Morse Code messages using a state machine. The active message can be switched between SOS and OK using physical button input.

The Smart Thermostat builds on those concepts to create a functioning thermostat prototype capable of monitoring temperature, adjusting a set point, switching between operating modes, displaying system information, and transmitting thermostat data through a serial connection.

## Smart Thermostat Features

- Off, heating, and cooling operating modes
- AHT20 temperature sensor using I2C communication
- Adjustable temperature set point using physical buttons
- Red and blue LED indicators for heating and cooling behavior
- 16x2 LCD displaying temperature, operating state, set point, date, and time
- UART serial communication for transmitting thermostat status
- State-machine-based control logic
- Periodic temperature and system status updates

## Morse Code State Machine

The Morse Code project demonstrates state-machine design using Raspberry Pi hardware. Red and blue LEDs represent dots and dashes while the LCD displays the active message.

The system supports:

- SOS and OK messages
- Physical button input to switch messages
- Separate states for dots, dashes, and timing pauses
- Threaded message transmission
- LCD output showing the active message

## Technologies

- Python
- Raspberry Pi
- GPIO
- I2C
- UART
- AHT20 temperature sensor
- 16x2 LCD display
- LEDs and physical buttons
- Python StateMachine
- GPIO Zero

## System Design

The Smart Thermostat uses three primary states:

- **Off** – Heating and cooling indicators are disabled.
- **Heating** – The red LED indicates heating behavior based on the current temperature and set point.
- **Cooling** – The blue LED indicates cooling behavior based on the current temperature and set point.

The thermostat begins with a default set point of 72°F. Physical buttons allow the user to cycle between operating modes and increase or decrease the target temperature.

Temperature data is collected from the AHT20 sensor through I2C. The LCD provides local system information, while UART communication sends the current state, temperature, and set point as a comma-delimited status record every 30 seconds.

## Technical Decisions

State machines were used to organize system behavior into clearly defined operating states and transitions. This made the hardware behavior easier to understand, debug, and extend.

The Raspberry Pi provided the GPIO, I2C, and UART interfaces required to integrate the thermostat's buttons, LEDs, display, temperature sensor, and serial communication.

For a potential production implementation, multiple embedded architectures were evaluated based on peripheral support, memory, connectivity, and future expansion requirements.

## Challenges and Solutions

One of the primary challenges was debugging the interaction between hardware and software. Wiring, GPIO connections, component behavior, and Python code had to be tested individually to determine the source of problems.

Breaking the system into smaller components made troubleshooting more manageable. State machines also helped isolate behavior by giving each operating state clearly defined actions and transitions.

## What I Learned

These projects strengthened my understanding of embedded systems and hardware/software integration. I gained hands-on experience with Python, Raspberry Pi hardware, GPIO, I2C, UART, sensors, LCD displays, physical inputs, and state-machine design.

The projects also strengthened my debugging skills. I learned to isolate hardware and software components and test them individually instead of assuming a problem originated from one specific part of the system.

## Project Files

- `Thermostat.py` – Smart Thermostat implementation
- `MorseCodeStateMachine.py` – Morse Code state-machine implementation
- `Morse-Code-State-Machine.drawio` – Editable Morse Code state-machine diagram
- `Smart-Thermostat-State-Machine.pdf` – Smart Thermostat state-machine documentation
- `Smart-Thermostat-Demo.mov` – Demonstration of the working Smart Thermostat prototype

## Project Demo

`Smart-Thermostat-Demo.mov` demonstrates the completed Smart Thermostat prototype operating with the physical Raspberry Pi hardware.
