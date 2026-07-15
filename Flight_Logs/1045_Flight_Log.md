# Flight Log – 10×4.5 Configuration

## Objective

Develop a stable flight controller for 10×4.5 propellers while maintaining the smooth flight characteristics achieved with the 8×4.5 configuration.

---

# Flight Platform

Frame:
- F450 Quadcopter

Flight Controller:
- Arduino Nano
- MPU6050

Motors:
- A2212 1000KV

ESC:
- 30A

Battery:
- 3S LiPo

Propellers:
- 10×4.5

---

# Initial Behaviour

Immediately after replacing the propellers:

- Severe oscillations during throttle increase.
- Poor hover stability.
- Aggressive oscillations during large pitch and roll commands.
- Slow recovery after stick release.
- Increased vibration reaching the MPU6050.

---

# Mechanical Improvements

Completed:

- Propeller balancing
- ESC calibration
- Frame balancing
- Vibration reduction

---

# PID Optimisation

The controller was tuned incrementally through multiple flight tests.

Adjustments included:

- Reduction of Roll/Pitch P gain.
- Gradual increase of Roll/Pitch D gain.
- Continuous evaluation after every flight.
- Verification of hover, medium stick, and aggressive manoeuvre performance.

---

# Final Flight Results

Hover

✅ Excellent

Small Stick Inputs

✅ Excellent

Medium Stick Inputs

✅ Excellent

Aggressive Roll

✅ Stable with rapid recovery

Aggressive Pitch

✅ Stable with rapid recovery

Yaw

✅ Stable

Landing

✅ Smooth

---

# Final Assessment

The final firmware demonstrated excellent stability throughout the flight envelope.

The larger propellers provided significantly greater lifting capability while maintaining smooth and predictable flight characteristics after systematic hardware optimisation and PID tuning.