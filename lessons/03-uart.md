# Lesson 03 — UART debugging

Status: planned. Prerequisites: GPIO and timers.

Goal: send a readable message from your firmware to a computer without Arduino's `Serial` object.

We will cover baud rate, transmit/receive registers, status flags, frame format, and the board's USB-to-serial connection. Register values and the upload/terminal workflow will be verified for your actual board and toolchain.

Exercise: transmit a short message, then a counter. Begin with a simple blocking implementation; later learn why blocking transmission can disrupt motor control.

Class workspace: `src/drivers/Uart.h`.

Review checkpoint: explain what makes a byte ready to transmit and what baud rate means.
