# Lesson 05 — Your encoder class

Status: planned. Prerequisite: working I²C driver.

Goal: separate sensor-specific logic from bus communication.

We previously sketched this possible interface:

```cpp
class AS5600Encoder {
public:
    void begin();
    float readAngleRadians();
};
```

This is an idea, not a finalized interface. Before implementing it, decide how callers will distinguish a valid measurement from a communication failure.

We will cover composing bytes into a reading, converting units, handling angle wraparound, estimating velocity from timed samples, and separating filtering from measurement.

Class workspace: `src/sensors/AS5600Encoder.h`.

Review checkpoint: explain the difference between the class and an instance, then show how your instance uses an I²C driver. Record a manual shaft rotation with motor power disconnected.
