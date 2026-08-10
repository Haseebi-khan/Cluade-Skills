# Example: Robotics / Drone Tutorial

**Input:**
> https://www.youtube.com/watch?v=EXAMPLE3 — "ArduPilot Flight Controller Setup" (2019). I'm a beginner. Is this tutorial still relevant?

Because the ask is explicitly "is this still relevant," this uses `templates/replacement_mode.md` shape rather than the full standard output.

**Abbreviated output shape:**

```markdown
# 🎥 Should You Watch This? ArduPilot Flight Controller Setup (2019)

Transcript available: yes | Duration: 41m

**Verdict:** PARTIALLY

**Reason:** The core concepts (what a flight controller does, PID tuning theory,
the pre-arm safety checklist) are unchanged and well explained. The specific
setup flow — which firmware version to flash and the exact Mission Planner UI
shown — has moved on: the firmware flashing step (12:30–19:00) refers to a
Mission Planner layout that's been reorganized in current releases (verified
against current ArduPilot documentation).

**Worth watching:** 0:00–12:30 (concepts, PID tuning theory), 24:00–35:00
(pre-arm checklist and first-flight safety practices — still directly applicable).

**Skip:** 12:30–19:00 (firmware flashing walkthrough — UI has changed).

## Recommended Path Instead
1. Watch 0:00–12:30 for the flight controller concepts and PID theory — still solid.
2. Follow the current official ArduPilot firmware installation guide for the
   actual flashing steps (linked from ardupilot.org) instead of 12:30–19:00.
3. Return to 24:00–35:00 for the pre-arm checklist — still accurate and
   important for safety.
4. Practice: flash a controller, run through the checklist, and do a
   controlled bench test (props off) before any real flight.

## Knowledge Check
1. Why does a flight controller need a pre-arm check before every flight?
2. What's the difference between P, I, and D in PID tuning, in your own words?
3. Why has the setup software's UI changing not affected the underlying PID
   theory the video teaches?
```

This example demonstrates replacement mode: a specific, evidence-based reason for PARTIALLY rather than a blanket "it's old," concrete timestamp ranges for what to watch vs. skip, and a path that mixes the still-valid parts of the video with a current external resource for the part that isn't.
