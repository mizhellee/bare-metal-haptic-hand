# Bare-metal haptic hand

A learning project for writing bare-metal C++ firmware on the ATmega2560 (Mega 2560 board), progressing from GPIO to a tendon-driven haptic hand.

## Learning approach

The aim is to understand and implement each layer of the firmware. The starting toolchain will use the AVR compiler, device headers, and standard startup support, without Arduino or SimpleFOC in the application. Custom startup code and linker configuration can come later.

The lessons below are a syllabus in progress. The C++ files are design placeholders, not working drivers. Interfaces and implementations will be developed during the lessons. No motor-driving implementation or hardware validation is included yet. The initial syllabus and scaffolds were prepared with AI assistance; future commits will record implementation and testing as they happen.

## Lessons

| Lesson | Topic | Status |
|---|---|---|
| [01](lessons/01-gpio.md) | Registers, bit operations, and GPIO | In progress: bit operations |
| [02](lessons/02-timers.md) | Timers and accurate timing | Planned |
| [03](lessons/03-uart.md) | Serial debugging with UART | Planned |
| [04](lessons/04-i2c.md) | I²C and the AS5600 | Planned |
| [05](lessons/05-encoder.md) | Your encoder class and velocity estimation | Planned |
| [06](lessons/06-motor-control.md) | PWM, calibration, FOC, and haptics | Planned |

## Folder guide

- `lessons/`: explanations, exercises, and review checkpoints. We will expand each lesson when you reach it.
- `src/`: your main program and class placeholders.
- `notes/`: local questions and observations, excluded from Git. Record publishable test results with the relevant lesson.

Keep motor power disconnected for the GPIO, timer, UART, and encoder lessons. Motor-power experiments will get their own procedure when the hardware drivers are ready.

This repository is a learning scaffold, not a deployable motor controller. A build configuration will be added during the first hardware lab.
