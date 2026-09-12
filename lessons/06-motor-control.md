# Lesson 06 — Your motor-control stack

Status: planned; this topic will be divided into smaller labs.

Goal: build toward your own motor controller and haptic response.

Planned sequence:

1. Configure and verify PWM signals without energizing the motor.
2. Understand the SimpleFOC Mini hardware input and enable behavior.
3. Establish a bounded motor test and calibration procedure.
4. Relate mechanical angle, pole pairs, sensor direction, and electrical angle.
5. Implement phase-voltage calculations and commutation.
6. Add spring and one-sided wall behavior.

The SimpleFOC Mini remains the power-driver hardware; your code replaces the software library. Motor parameters, timing, fault handling, and output limits must be established before powered experiments.

Class workspaces: `src/drivers/Pwm3Phase.h`, `src/control/BldcController.h`, and `src/control/HapticController.h`.

Review checkpoint: trace a sensor reading through your code to a phase command, and explain how output is disabled. A working compile does not establish stable physical motor behavior.
