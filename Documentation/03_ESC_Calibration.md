# ESC Calibration

## Overview

Electronic Speed Controllers (ESCs) translate throttle commands from the flight controller into motor speed. For stable flight, all ESCs must interpret the throttle signal identically. If one ESC starts its motor earlier or later than the others, the quadcopter can become unstable even with correct PID tuning.

---

# Why Calibration is Necessary

Different ESCs may store different throttle ranges from manufacturing or previous calibration.

This can lead to:

- Motors starting at different throttle levels
- Unequal motor RPM
- Poor hover stability
- Unwanted drifting
- Increased oscillations
- Difficult PID tuning

Calibrating all ESCs together ensures every ESC learns the same minimum and maximum throttle values.

---

# Hardware Used

- 4 × 30A ESCs
- Arduino r3
- YMFC-AL Flight Controller
- 3S LiPo Battery

---

# Calibration Procedure

1. Upload the ESC calibration sketch.
2. Disconnect all propellers for safety.
3. Connect all four ESC signal wires to the Arduino.
4. Power the flight controller.
5. Connect the LiPo battery.
6. Wait for the calibration beeps.
7. Disconnect the battery.
8. Upload the normal flight controller firmware again.

---

# Safety Precautions

- Remove all propellers before calibration.
- Verify correct wiring before connecting the battery.
- Never touch the motors during calibration.
- Use a fully charged battery.

---

# Expected Result

After successful calibration:

- All motors begin spinning at nearly the same throttle.
- Motors respond uniformly.
- Hover becomes smoother.
- PID tuning becomes more consistent.
- Overall flight stability improves.

---

# Practical Observation

Before calibration:

- Slight differences in motor response were observed.
- Drone required more PID compensation to remain stable.

After calibrating all four ESCs simultaneously:

- Motors responded much more uniformly.
- Hover became smoother.
- Oscillations reduced.
- PID tuning became easier and more predictable.

ESC calibration proved to be an important step before performing the final PID tuning for the 10×4.5 propeller configuration.

---

# Notes

ESC calibration should always be performed:

- After replacing an ESC
- After replacing the flight controller
- Before beginning PID tuning
- Whenever inconsistent motor response is observed

###### The calibration firmware used in this project is available in:

Source/ESC_Calibration/