# Experiment 01 – PID Tuning

## Objective

The objective of this experiment was to obtain a stable and responsive flight controller by systematically tuning the Proportional (P), Integral (I), and Derivative (D) gains of the YMFC-AL Flight Controller.

The tuning process was carried out separately for the 8×4.5 and 10×4.5 propeller configurations.

---

# Test Platform

Frame:
- F450 Quadcopter Frame

Flight Controller:
- Arduino r3
- MPU6050 IMU

Motors:
- A2212 1000KV

ESC:
- 30A ESC

Battery:
- 3S LiPo

Propellers Tested:
- 8×4.5
- 10×4.5

---

# Initial PID Values

## Roll

P = 1.45

I = 0.04

D = 18.0

---

## Pitch

P = 1.45

I = 0.04

D = 18.0

---

## Yaw

P = 4.00

I = 0.02

D = 0.00

---

# Understanding the Problem

The original PID values worked well with the 8×4.5 propellers but became unsuitable after replacing them with 10×4.5 propellers.

The larger propellers generated:

- Higher thrust
- Greater rotational inertia
- Stronger control response
- Increased oscillation tendency

As a result, the quadcopter became unstable.

---

# Initial Behaviour

The following behaviour was observed during the first flights using 10×4.5 propellers:

- Oscillations appeared immediately while increasing throttle.
- Hover stability was poor.
- Aggressive pitch and roll commands produced severe oscillations.
- Recovery after stick release was slow.
- Oscillations increased until pilot intervention.

---

# Mechanical Improvements Before PID Tuning

Before modifying the controller gains, hardware-related issues were eliminated.

The following improvements were completed:

- Propellers individually balanced.
- Electrical tape used to reduce residual imbalance.
- All four ESCs calibrated simultaneously.
- Frame balance corrected.
- Hardware inspected for vibration sources.

These changes significantly reduced mechanical vibration reaching the MPU6050.

---

# PID Tuning Strategy

PID tuning was performed using an incremental approach.

Only one parameter was modified at a time.

After every change the quadcopter was tested for:

- Hover stability
- Small stick response
- Medium stick response
- Aggressive manoeuvres
- Recovery after stick release

---

# PID Evolution

| Stage | Roll/Pitch P | Roll/Pitch I | Roll/Pitch D | Observation |
|--------|--------------|--------------|--------------|-------------|
| Original | 1.45 | 0.04 | 18 | Stable with 8×4.5, unstable with 10×4.5 |
| Test 1 | 1.30 | 0.04 | 18 | Reduced throttle oscillations |
| Test 2 | 1.30 | 0.04 | 20 | Better damping |
| Test 3 | 1.30 | 0.04 | 22 | Small oscillations after aggressive stick inputs |
| Final | 1.30 | 0.04 | 23 | Stable recovery with excellent damping |

---

# Final Flight Behaviour

After the final tuning:

- Stable hover
- Smooth small stick response
- Immediate stabilization after medium stick inputs
- Rapid recovery after aggressive pitch and roll
- No throttle-induced oscillations
- Excellent overall controllability

---

# Final PID Values

## Roll

P = 1.30

I = 0.04

D = 23.0

---

## Pitch

P = 1.30

I = 0.04

D = 23.0

---

## Yaw

P = 4.00

I = 0.02

D = 0.00

---

# Conclusions

Several important observations were made during this experiment:

- Larger propellers require different PID values.
- Mechanical vibration should always be reduced before PID tuning.
- ESC calibration improves consistency between motors.
- Increasing Derivative gain significantly improved recovery after aggressive manoeuvres.
- Systematic testing produced far better results than random parameter changes.