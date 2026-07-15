# Changelog

All notable changes to this project are documented in this file.

---

# Version 1.0 – Original YMFC-AL

Date: Original Release

### Based on
- Original YMFC-AL Flight Controller by Joop Brokking.

### Features
- Arduino Uno based flight controller
- MPU6050 IMU
- Auto-level mode
- PID stabilization
- 250 Hz control loop
- Battery voltage compensation

Status:
- Reference firmware.

---

# Version 2.0 – Stable 8×4.5 Configuration


### Hardware
- F450 Frame
- A2212 1000KV Motors
- 30A ESCs
- 3S LiPo
- 8×4.5 Propellers

### Changes
- Tuned Roll PID
- Tuned Pitch PID
- Optimized D gain
- Improved hover stability
- Eliminated oscillations during normal flight
- Stable auto-level behavior
- Improved recovery after stick release

### Result
- Smooth hover
- Stable pitch and roll
- Reliable baseline firmware

---

# Version 3.0 – Stable 10×4.5 Configuration


### Hardware
- F450 Frame
- A2212 1000KV Motors
- 30A ESCs
- 3S LiPo
- 10×4.5 Propellers

### Initial Problems
- Severe oscillations
- Aggressive wobble after large stick inputs
- Poor recovery
- Propeller vibration
- ESC mismatch

### Engineering Changes
- ESCs calibrated together
- Propellers dynamically balanced
- Frame balance corrected
- Multiple PID tuning iterations
- Reduced Roll/Pitch P gain
- Increased Roll/Pitch D gain
- Auto-level tuning evaluated
- Flight-tested after every modification

### Final Results
- Stable hover
- No oscillations during small stick inputs
- Smooth medium stick response
- Stable aggressive pitch and roll recovery
- Improved damping after rapid stick reversals
- Flight characteristics comparable to the 8×4.5 setup

Status:
- Stable release for 10×4.5 propellers.

---

# Future Plans

- GPS Hold
- Altitude Hold
- Return-to-Home
- Telemetry
