# Project Journey

## Introduction

This project began with the objective of understanding the complete working of an Arduino-based flight controller instead of simply using an existing commercial solution.

The YMFC-AL Flight Controller by Joop Brokking was selected as the foundation because of its simplicity, open-source nature, and educational value.

The goal was not only to build a working quadcopter but also to understand every stage of the control system, identify practical problems during real flight, and improve the firmware through systematic engineering.

---

# Hardware Platform

The project was built using:

- F450 Quadcopter Frame
- Arduino r3
- MPU6050 IMU
- FlySky FS-iA6B Receiver
- A2212 1000KV Brushless Motors
- 30A ESCs
- 3S LiPo Battery

Two propeller configurations were developed:

- 8×4.5
- 10×4.5

---

# Phase 1 – Building the Flight Controller

The first stage involved assembling the complete flight controller hardware.

This included:

- Wiring the MPU6050
- Connecting the receiver
- Wiring all ESCs
- Configuring the YMFC setup sketch
- Calibrating the MPU6050
- Verifying receiver channels
- Performing the first motor tests

Once the hardware was operational, the quadcopter was ready for its first hover tests.

---

# Phase 2 – Accelerometer Offset Investigation

During early testing with the 8×4.5 propellers, the quadcopter consistently tilted during takeoff even though it was placed on a perfectly level surface.

Instead of immediately modifying PID values, the control loop was investigated using the Arduino IDE Serial Monitor.

The following parameters were continuously monitored:

- GR
- GP
- GAR
- GAP
- AR
- AP
- PR
- PP

The investigation revealed that the accelerometer angle estimates contained a constant offset.

Although physically level, the controller believed the quadcopter was tilted.

This caused the PID controller to continuously generate correction commands, increasing motor output unnecessarily and making the aircraft unstable.

After several unsuccessful calibration attempts, fixed offset compensation values were introduced directly into the accelerometer angle calculations.

Once these offsets were applied:

- Accelerometer angles remained centered around zero.
- PID outputs remained close to zero while stationary.
- Motor outputs became balanced.
- Stable takeoff and hover were achieved.

This became the first major engineering improvement of the project.

---

# Phase 3 – Development of the 8×4.5 Configuration

Following the accelerometer correction, the 8×4.5 configuration demonstrated:

- Stable hover
- Predictable control
- Reliable recovery
- Smooth handling

This version became the baseline firmware for future development.

---

# Phase 4 – Transition to 10×4.5 Propellers

The next objective was to increase lifting capability by replacing the propellers with 10×4.5.

Immediately after installation, the quadcopter exhibited severe oscillations.

Initially, oscillations appeared even while simply increasing the throttle without any roll or pitch commands.

Once hover became possible, aggressive roll and pitch manoeuvres still produced continuous oscillations that required pilot intervention.

The original PID values were clearly unsuitable for the increased thrust and rotational inertia of the larger propellers.

---

# Phase 5 – Mechanical Improvements

Before changing the controller gains, possible mechanical causes were investigated.

The following improvements were implemented:

- Individual propeller balancing
- Reduction of vibration using balancing tape
- ESC calibration
- Frame balancing
- Hardware inspection

These modifications significantly reduced vibration transmitted to the flight controller.

---

# Phase 6 – PID Optimisation

After the mechanical improvements, systematic PID tuning began.

Rather than changing multiple parameters simultaneously, only one variable was modified before each flight.

Numerous flight tests were conducted while observing:

- Hover stability
- Small stick response
- Medium stick response
- Aggressive manoeuvres
- Recovery after stick release

The proportional gain was reduced to decrease controller aggressiveness.

The derivative gain was gradually increased to improve damping and suppress oscillations.

Every modification was followed by repeated flight testing before proceeding further.

---

# Phase 7 – Final Results

The final firmware demonstrated:

- Stable hover
- Excellent small stick response
- Stable medium stick manoeuvres
- Rapid recovery after aggressive pitch and roll
- Elimination of throttle-induced oscillations
- Smooth and predictable handling

The final 10×4.5 configuration achieved flight characteristics comparable to the tuned 8×4.5 configuration while providing significantly greater lifting capability.

---

# Lessons Learned

Throughout this project several important engineering principles became evident:

- Hardware issues should always be eliminated before software tuning.
- Mechanical vibration has a significant impact on flight controller performance.
- ESC calibration greatly improves motor synchronization.
- Propeller balancing reduces sensor noise.
- Serial debugging is invaluable for understanding controller behaviour.
- PID tuning should always be performed methodically, changing one parameter at a time.
- Larger propellers require different controller tuning because of increased thrust and rotational inertia.

---

# Contributors

This project was collaboratively developed by:

**Parmeet Singh** and **Pahul Sodhi**

through iterative design, hardware integration, embedded programming, systematic debugging, PID optimisation, and extensive real-world flight testing.

# Acknowledgements

This project is based on the original YMFC-AL Flight Controller developed by **Joop Brokking**, whose educational work made this project possible.

We gratefully acknowledge his contribution to the open-source embedded systems and drone community.