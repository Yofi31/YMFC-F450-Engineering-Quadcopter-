# Troubleshootig

This document lists common issues encountered during the development of the YMFC-AL Flight Controller along with their possible causes and solutions.

---

# Drone Flips Immediately After Arming

## Possible Causes

- Incorrect motor numbering
- Wrong propeller orientation
- Incorrect motor rotation direction
- Incorrect ESC connections
- Receiver channels mapped incorrectly

## Solution

- Verify motor numbering.
- Verify propeller orientation.
- Check motor rotation.
- Confirm receiver channel assignments.
- Verify wiring according to the wiring documentation.

---

# Drone Tilts During Takeoff

## Possible Causes

- Frame not level
- Accelerometer offset
- Incorrect IMU calibration
- Unequal motor thrust

## Solution

- Recalibrate the IMU.
- Check accelerometer offsets.
- Verify ESC calibration.
- Inspect motor performance.
- Ensure the frame is level before arming.

---

# Drone Oscillates During Hover

## Possible Causes

- Excessive Proportional (P) gain
- Unbalanced propellers
- Frame vibration
- Loose flight controller mounting

## Solution

- Reduce P gain gradually.
- Balance all propellers.
- Check frame for loose components.
- Reduce mechanical vibration reaching the MPU6050.

---

# Drone Oscillates During Aggressive Maneuvers

## Possible Causes

- Insufficient Derivative (D) gain
- Large propeller inertia
- Excessive vibration

## Solution

- Increase D gain gradually.
- Perform flight testing after every adjustment.
- Ensure propellers are properly balanced.
- Recalibrate ESCs if required.

---

# Slow Recovery After Stick Release

## Possible Causes

- Low Derivative gain
- Incorrect PID tuning

## Solution

- Increase D gain incrementally.
- Test hover and aggressive maneuvers after each change.

---

# Motors Do Not Start Together

## Possible Causes

- ESCs not calibrated
- Different throttle ranges stored by ESCs

## Solution

- Perform simultaneous ESC calibration for all four ESCs.

---

# Excessive Vibrations

## Possible Causes

- Damaged propeller
- Unbalanced propeller
- Bent motor shaft
- Loose frame

## Solution

- Balance propellers.
- Replace damaged propellers.
- Tighten all frame hardware.
- Inspect motors for damage.

---

# MPU6050 Not Detected

## Possible Causes

- Loose wiring
- Incorrect I2C connections
- Incorrect device address

## Solution

- Verify SDA and SCL connections.
- Check VCC and GND.
- Run the setup sketch again.
- Verify the detected I2C address.

---

# Receiver Not Responding

## Possible Causes

- Incorrect receiver wiring
- Receiver not bound
- Incorrect channel mapping

## Solution

- Verify receiver wiring.
- Bind the receiver again.
- Check receiver channel assignments using the setup sketch.

---

# Lessons Learned

Throughout the development of this project, several practical observations were made:

- Always eliminate mechanical issues before modifying PID values.
- Calibrate ESCs before beginning PID tuning.
- Balance propellers to reduce IMU vibration.
- Change only one parameter at a time.
- Validate every modification through repeated flight testing.
- Use Serial Monitor data to understand controller behavior instead of relying only on visual observations.
- Larger propellers require different PID tuning because of increased thrust and rotational inertia.
- Systematic testing produces significantly better results than random tuning.

---

# Additional Resources

For further information, refer to:

- Hardware Documentation
- Wiring Documentation
- ESC Calibration Guide
- PID Tuning Guide
- Flight Testing Report
- Project Journey