# Lesson 01 — Registers, bits, and GPIO

Status: in progress — registers and bit operations. Hardware implementation not started.

## Goal

Configure a digital output and control an LED without Arduino functions.

## Starting concepts

A hardware register is a special location whose bits configure hardware or report its state. A pin's direction and output state are controlled through registers.

On this microcontroller, a GPIO port has a group of pins controlled by 8-bit registers. The direction register is named `DDRx`, where `x` is the port letter. In ordinary GPIO operation, a direction bit of 1 configures the corresponding pin as an output; 0 selects input. `PORTx` controls the output latch (and has a pull-up role when configured as input). `PINx` reads the pin state. Peripheral functions can also take control of pins; we will examine that when configuring real hardware.

Source: [Microchip ATmega640/1280/1281/2560/2561 datasheet, I/O Ports](https://ww1.microchip.com/downloads/en/DeviceDoc/ATmega640-1280-1281-2560-2561-Datasheet-DS40002211A.pdf).

## Part A — Numbering bits

An 8-bit value has positions 0 through 7, counted from the right:

```text
Position:  7 6 5 4 3 2 1 0
Value:     0 0 0 0 0 0 0 0
```

`1u << 3` shifts the binary value 1 three places left, giving the mask `00001000`. The `u` means unsigned. A mask identifies the bit or bits an operation should affect.

## Part B — Set a bit without disturbing other bits

Bitwise OR (`|`) returns 1 at a position if either operand has a 1 there:

```text
Original:  00100000
Mask:      00001000
OR result: 00101000
```

In C++:

```cpp
value |= (1u << 3);
```

This is shorthand for `value = value | (1u << 3);`. The existing bit 5 stays set. In contrast, assigning `value = (1u << 3);` would replace the whole value and clear bit 5.

These examples use an ordinary variable. We will apply the operation to a real GPIO register only after checking the board's pin mapping. Do not assume the same read/modify/write pattern is appropriate for every hardware register: status and command registers may have special write behavior.

## Exercise 1 — Predict before running

Given:

```cpp
unsigned char value = 0b00000010;
value |= (1u << 5);
```

1. Write the final eight-bit binary value.
2. Explain whether bit 1 is preserved and why.
3. How would the result differ if the second line used `=` instead of `|=`?

Leave the answer in your local learning log or explain it during the lesson. Next we will learn to clear a bit, then configure a real output.

Our C++ application has an explicit entry point:

```cpp
int main() {
    // Configure hardware.
    while (true) {
        // Run the application.
    }
}
```

## What we will cover

- Binary values and bit positions.
- Bitwise AND, OR, XOR, NOT, and shifts.
- Setting or clearing one bit while preserving the others.
- Reading device documentation and identifying the LED's actual port and bit.
- Configuring an output and observing its state.

## Your work

First write the register operations directly in `src/main.cpp`. After they work and you can explain them, decide what belongs in `src/drivers/Gpio.h`.

## Review checkpoint

Explain the difference between choosing a pin's direction and setting its output state. Record the code and observed LED behavior in the learning log.
