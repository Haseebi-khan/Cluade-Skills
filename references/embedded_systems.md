# Embedded Systems Teaching Mode

Use for microcontrollers, STM32, FreeRTOS, peripherals, electronics/software interfaces, and real-time systems.

## Hardware/software boundary

```text
Physical signal
 ↓
Sensor / peripheral
 ↓
Register / HAL / driver
 ↓
Firmware
 ↓
Application logic
```

Show where each abstraction layer lives.

## Timing
Explain clock, period, frequency, sampling, interrupt latency, scheduling, and deadlines when relevant. Use formulas.

## Peripherals
For GPIO, timers, PWM, ADC, UART, SPI, I2C, CAN, etc. explain physical purpose, electrical/data behavior, register/HAL abstraction, firmware flow, and common failure modes.

## Interrupts
Explain event, interrupt request, handler, shared state, latency, and synchronization. Avoid unsafe concurrency assumptions.

## RTOS
For FreeRTOS explain task, scheduler, priority, queue, semaphore, mutex, timing, and blocking/non-blocking behavior.

## Reliability
Mention watchdogs, brownouts, race conditions, stack size, memory limits, fault handling, and deterministic timing when relevant.
