# Flight Testing

## Objective

The objective of flight testing was to validate the performance, stability, and reliability of the YMFC-AL Flight Controller after hardware modifications and PID tuning.

All tests were conducted incrementally to ensure safe operation while observing the effect of each modification.

---

# Test Platform

Frame:
- F450 Quadcopter Frame

Flight Controller:
- Arduino r3
- MPU6050 IMU

Motors:
- A2212 1000KV Brushless Motors

ESC:
- 30A ESC

Battery:
- 3S LiPo

Propellers Tested:
- 8×4.5
- 10×4.5

---

# Testing Procedure

Every flight followed the same sequence:

1. Verify propeller orientation.
2. Verify motor direction.
3. Check receiver inputs.
4. Check battery voltage.
5. Arm the flight controller.
6. Hover test.
7. Small stick input test.
8. Medium stick input test.
9. Aggressive maneuver test.
10. Landing inspection.

---

# Test Parameters

During every flight the following characteristics were observed:

- Hover stability
- Roll response
- Pitch response
- Yaw response
- Recovery after stick release
- Oscillations
- Motor vibration
- ESC synchronization
- Overall controllability

---

# 8×4.5 Propeller Results

Hover:
- Stable

Small stick inputs:
- Smooth response

Medium stick inputs:
- Controlled with minimal overshoot

Aggressive stick inputs:
- Stable after accelerometer offset correction

Overall Result:
- Reliable and predictable flight.

---

# 10×4.5 Propeller Results

Initial Testing

Observed behaviour:

- Oscillations during throttle increase.
- Large oscillations during aggressive roll and pitch.
- Slow recovery after rapid stick reversals.

After Hardware Improvements

Performed:

- ESC calibration
- Propeller balancing
- Frame balancing

Result:

- Hover improved.
- Oscillations reduced.

After PID Optimisation

Observed behaviour:

- Stable hover.
- Smooth small stick response.
- Stable medium stick manoeuvres.
- Rapid recovery after aggressive pitch and roll.
- No continuous oscillations.
- Predictable control throughout the flight.

---

# Final Assessment

The final firmware demonstrated:

- Excellent hover stability.
- Responsive control.
- Stable recovery after aggressive manoeuvres.
- Reliable operation with both 8×4.5 and 10×4.5 propellers.

The project successfully achieved a stable Arduino-based flight controller capable of flying larger propellers through systematic hardware optimisation and PID tuning.