# Lesson 02 — Timers

Status: planned. Prerequisite: GPIO.

Goal: create a repeatable time interval without Arduino's `delay()`.

We will cover the clock source, counters, prescalers, compare matches, polling, and interrupts. Before choosing register values, we will confirm the board clock and derive the required counts.

Exercise: use a timer to blink the LED at a chosen interval, then explain how changing the prescaler affects it.

Class workspace: `src/drivers/Timer.h`.

Review checkpoint: distinguish a timer event from software noticing that event; record the expected and observed timing.
