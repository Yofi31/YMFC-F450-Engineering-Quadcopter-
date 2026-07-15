# Flight Log – 8×4.5 Configuration

## Objective

Validate the stability of the YMFC-AL Flight Controller using 8×4.5 propellers after correcting the accelerometer offset.

---

# Flight Platform

Frame:
- F450 Quadcopter

Flight Controller:
- Arduino r3
- MPU6050

Motors:
- A2212 1000KV

ESC:
- 30A

Battery:
- 3S LiPo

Propellers:
- 8×4.5

---

# Initial Behaviour

During the initial flights, the quadcopter consistently tilted during takeoff despite being placed on a perfectly level surface.

Serial Monitor debugging revealed constant offsets in the accelerometer angle calculations, causing the PID controller to continuously generate correction commands.

---

# Engineering Changes

Implemented:

- Accelerometer offset compensation
- Sensor verification
- Multiple calibration attempts
- Flight testing after every modification

---

# Flight Results

Hover

✅ Stable

Small Stick Inputs

✅ Smooth

Medium Stick Inputs

✅ Stable

Aggressive Stick Inputs

✅ Stable

Landing

✅ Controlled

---

# Final Observation

The accelerometer offset compensation successfully eliminated the false attitude error.

The quadcopter achieved stable hover and predictable flight behaviour, becoming the baseline firmware for future development.