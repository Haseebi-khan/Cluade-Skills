# Example: Electronics Tutorial

**Input:**
> Analyze this video: https://www.youtube.com/watch?v=EXAMPLE4 — "Getting Started with ESP32" (2018). Teach me everything important in under 20 minutes, replace anything outdated.

**Abbreviated output shape:**

```markdown
# 🎥 Video-to-Mastery: Getting Started with ESP32

Published: 2018 | Duration: 45m | Transcript available: yes

## Verdict
Freshness: ~50/100 — the hardware fundamentals (GPIO, pinout basics, power
requirements) are unchanged; the development environment setup is outdated.
Difficulty: Beginner | Educational value: High for hardware concepts.

## What's Outdated
Original video: installs the ESP32 board package into the Arduino IDE via a
manually-added boards-manager URL and an older IDE version's menu layout.
Current approach: the current Arduino IDE (2.x) install flow uses the same
boards-manager-URL mechanism but a reorganized menu — verified against current
Arduino/ESP32 documentation; alternatively, PlatformIO is now a common
beginner-friendly alternative to the Arduino IDE for ESP32 work.
Concept that remains valid: you still need to add the ESP32 board definitions
before you can flash it from the IDE — only the menu path changed.

## Learn This Instead
### P0 — GPIO and pinout basics (unchanged, taught as shown)
### P0 — Current IDE/board-package setup (updated)
### P1 — PlatformIO as an alternative (not in the original video, worth
mentioning since it's now a common beginner path)

## Modern Implementation
(current boards-manager URL and current menu path, verified against docs)

## Common Mistakes
Wrong board variant selected in the IDE; not holding BOOT during flashing on
some board revisions; powering peripherals directly from a GPIO pin instead of
through appropriate regulation.

## Crash Course Time Estimate
Original: 45m | Useful: ~28m | Compressed: ~18m

## Practice
Mission: blink an LED, then read a button press and print it to serial.
Step 1: install current toolchain. Step 2: wire LED + resistor. Step 3: flash
blink sketch. Step 4: add button input. Success condition: LED toggles on
button press.

## Knowledge Check
1. Why does a GPIO pin need current-limiting before driving an LED directly?
2. The old video adds a boards-manager URL from an older IDE menu — where does
   this live in the current IDE?
3. What's one reason you might choose PlatformIO over the Arduino IDE?

## Next Step
Once comfortable flashing and basic I/O work, WiFi/BLE on the ESP32 is a
natural next step — the chip's main differentiator over simpler boards.
```

This example demonstrates: separating hardware-fundamentals content (durable) from tooling/IDE content (fast-moving), and surfacing a currently-relevant alternative (PlatformIO) that didn't exist in the learner's original source but is genuinely useful context.
