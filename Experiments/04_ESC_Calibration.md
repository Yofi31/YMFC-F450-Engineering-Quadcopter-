# Experiment 04 – ESC Calibration

## Objective

The objective of this experiment was to synchronize all four Electronic Speed Controllers (ESCs) by calibrating their throttle ranges simultaneously.

Proper ESC calibration ensures that each ESC interprets the same throttle command identically, resulting in uniform motor response and improved flight stability.

---

# Test Platform

Frame:
- F450 Quadcopter Frame

Flight Controller:
- Arduino r3

ESC:
- 4 × 30A ESC

Motors:
- A2212 1000KV Brushless Motors

Battery:
- 3S LiPo

---

# Why ESC Calibration is Important

Although all four ESCs were identical, slight differences in their stored throttle endpoints could cause:

- Different motor startup speeds
- Unequal motor RPM
- Uneven thrust
- Poor hover stability
- Difficult PID tuning

Calibrating all ESCs together ensures that every ESC stores identical minimum and maximum throttle values.

---

# Initial Observation

Before calibration:

- Minor differences in motor startup timing were observed.
- Hover required additional corrections from the PID controller.
- Overall motor synchronization was not optimal.

These effects became more noticeable after switching to the larger 10×4.5 propellers.

---

# Calibration Procedure

The dedicated ESC calibration firmware included in this repository was uploaded to the Arduino Nano.

All four ESCs were calibrated simultaneously using the same throttle range.

After calibration, the normal YMFC-AL flight controller firmware was uploaded again.

---

# Results

After calibration:

- All four motors started at nearly the same throttle value.
- Motor response became more uniform.
- Hover became smoother.
- PID tuning became more consistent.
- Oscillations were reduced.

Although ESC calibration alone did not completely eliminate oscillations, it provided a more consistent mechanical platform for subsequent PID tuning.

---

# Engineering Observations

ESC calibration was one of several mechanical improvements completed before modifying PID values.

The complete optimisation process consisted of:

- ESC calibration
- Propeller balancing
- Frame balancing
- PID optimisation

Performing these hardware improvements first ensured that PID tuning addressed actual controller behaviour rather than compensating for mechanical inconsistencies.

---

# Conclusion

ESC calibration significantly improved motor synchronization and contributed to the final stable flight characteristics.

This experiment reinforced an important engineering principle:

**Mechanical consistency should always be established before controller tuning begins.**