# PID Tuning

## Overview

A quadcopter continuously compares its desired orientation with its measured orientation using the MPU6050 gyroscope and accelerometer. The PID controller calculates the correction required to stabilize the aircraft by adjusting the speed of each motor independently.

The quality of the PID tuning directly affects hover stability, maneuverability, recovery after stick inputs, and overall flight performance.

---

# Understanding PID

## Proportional Gain (P)

The proportional term reacts to the current error.

Higher P:
- Faster response
- More aggressive corrections
- Can cause oscillations if too high

Lower P:
- Slower response
- Softer control
- Less chance of oscillation

---

## Integral Gain (I)

The integral term corrects long-term accumulated error.

Higher I:
- Better long-term stability
- Holds angle more accurately
- Can become sluggish if excessive

Lower I:
- Faster feel
- May slowly drift over time

---

## Derivative Gain (D)

The derivative term reacts to the rate of change of error.

Higher D:
- Dampens oscillations
- Smooth recovery after rapid movements
- Too much D can introduce noise and motor heating

Lower D:
- Faster response
- Poor damping
- Oscillations may continue after aggressive stick inputs

---

# 8045 Propeller Tuning

## Initial Problem

During testing with 8×4.5 propellers, the drone consistently tilted and became unstable during takeoff despite repeated sensor calibration.

The instability was traced using the Arduino IDE Serial Monitor.

The following variables were monitored:

- GR (Gyroscope Roll)
- GP (Gyroscope Pitch)
- GAR (Gyroscope Accelerometer Roll)
- GAP (Gyroscope Accelerometer Pitch)
- AR (Accelerometer Roll)
- AP (Accelerometer Pitch)
- PR (PID Roll Output)
- PP (PID Pitch Output)

---

## Root Cause

When the drone was placed on a perfectly flat surface:

- GAR and GAP contained a constant offset.
- This caused AR and AP to settle around non-zero values.
- PR and PP continuously increased while trying to correct an error that did not actually exist.

Eventually the PID outputs reached their maximum limit (approximately ±400), causing unequal motor thrust.

This resulted in unstable takeoff and poor flight characteristics.

Repeated accelerometer calibration did not eliminate the offset.

---

## Solution

Instead of allowing the offset to propagate through the control loop, experimentally determined correction values were introduced directly into the GAR and GAP calculations.

This removed the accelerometer bias before it entered the PID controller.

After implementing these offsets:

- GAR and GAP fluctuated around zero.
- AR and AP remained centered near zero.
- PR and PP stayed close to zero during hover.
- Motor outputs became balanced.

This modification significantly improved hover stability and produced reliable flight using 8×4.5 propellers.

---

# 10×4.5 Propeller Tuning

## Initial Behaviour

After replacing the propellers with 10×4.5, the drone immediately became unstable.

Unlike the 8×4.5 configuration, oscillations appeared even while increasing throttle without giving any roll or pitch commands.

The larger propellers generated considerably higher thrust and rotational inertia, making the original PID values unsuitable.

---

## Initial Investigation

The following possible causes were investigated:

- Incorrect center of gravity
- Propeller orientation
- Motor direction
- Frame balance
- ESC synchronization
- Sensor calibration
- Mechanical vibration
- PID tuning

Mechanical problems were corrected before modifying software.

---

## Mechanical Improvements

The following improvements were performed before continuing PID tuning:

- Propellers individually balanced.
- Electrical tape used to eliminate residual imbalance.
- All four ESCs calibrated simultaneously.
- Frame inspected for vibration sources.

These changes noticeably reduced vibration and improved hover consistency.

---

## PID Tuning Process

PID tuning was performed incrementally.

Only one parameter was modified at a time before performing another flight test.

The tuning sequence followed was:

1. Reduce Proportional gain to decrease aggressive oscillations.
2. Test hover.
3. Test small stick inputs.
4. Test medium stick inputs.
5. Test aggressive stick inputs.
6. Increase Derivative gain gradually to improve damping.
7. Repeat flight testing after every change.

Auto-level gains were intentionally left unchanged because the remaining oscillations were determined to originate from insufficient damping rather than excessive leveling correction.

---

## Final Flight Performance

After the final tuning:

- Stable hover.
- No oscillations during small stick inputs.
- Immediate stabilization after medium stick inputs.
- Aggressive roll and pitch commands recovered rapidly.
- Continuous forward-backward and left-right stick movements no longer caused uncontrolled oscillations.
- Overall control became smooth and predictable.

The flight characteristics became comparable to the previously tuned 8×4.5 configuration while retaining the increased lifting capability of the larger propellers.

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

# Key Engineering Lessons

- Mechanical problems should always be corrected before software tuning.
- ESC calibration should be completed before PID tuning.
- Balanced propellers greatly reduce unwanted vibrations.
- Modify only one parameter at a time.
- Test after every change.
- Larger propellers require different PID values because of increased thrust and rotational inertia.
- Careful observation and systematic testing are more effective than randomly changing PID values.


| Stage         | Roll/Pitch P | Roll/Pitch D | Observation                                   |
| ------------- | -----------: | -----------: | --------------------------------------------- |
| Original YMFC |         1.45 |           18 | Stable with 8×4.5, oscillated with 10×4.5     |
| Test 1        |         1.30 |           18 | Reduced throttle oscillations                 |
| Test 2        |         1.30 |           20 | Better recovery                               |
| Test 3        |         1.30 |           22 | Only slight wobble after aggressive inputs    |
| Final         |     **1.30** |       **23** | Stable hover and aggressive maneuver recovery |
