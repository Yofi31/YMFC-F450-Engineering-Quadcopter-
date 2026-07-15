# YMFC-AL Flight Controller Project

An enhanced version of Joop Brokking's YMFC-AL (Your Multicopter Flight Controller - Auto Level) developed for an F450 quadcopter using an Arduino Uno, MPU6050, FlySky FS-iA6B receiver, A2212 1000KV motors, 30A ESCs, and both 8×4.5 and 10×4.5 propellers.

This repository documents the complete development process, hardware setup, flight testing, PID tuning, and firmware evolution from the original YMFC-AL code to a stable flight controller tuned specifically for this platform.

###### ####### Before the first flight:

1. Upload the Setup sketch.
2. Upload the ESC Calibration sketch.
3. Calibrate all four ESCs.
4. Upload the desired Flight Controller firmware.


---

## Hardware

### Flight Controller
- Arduino Uno R3

### Sensors
- MPU6050 (Gyroscope + Accelerometer)

### Radio System
- FlySky FS-i6 Transmitter
- FlySky FS-iA6B Receiver

### Frame
- F450 Quadcopter Frame

### Motors
- A2212 1000KV Brushless Motors (×4)

### ESCs
- 30A SimonK/BLHeli Compatible ESCs (×4)

### Propellers
- 8×4.5 (Initial Stable Configuration)
- 10×4.5 (Final Tuned Configuration)

### Battery
- 3S LiPo (11.1V)

### Firmware Base
- Joop Brokking's YMFC-AL Flight Controller

---

## Features
- Auto-level stabilization using MPU6050
- PID-based attitude stabilization
- Receiver interrupt-based PWM input
- ESC PWM output at 250 Hz
- Battery voltage compensation
- ESC calibration support
- Manual PID tuning for different propeller sizes
- Multiple firmware versions preserved
- Complete project documentation

---

## Repository Structure

YMFC_Project/
│
├── Documentation/
├── Experiments/
├── Flight_Logs/
├── Notes/
├── Photos/
├── Source/
│   ├── V1_Original/
│   ├── V2_8045_Stable/
│   └── V3_1045_Final/
├── Videos/
├── README.md
├── CHANGELOG.md
└── LICENSE

---

## Firmware Versions

### V1_Original

Original YMFC-AL flight controller firmware by Joop Brokking without any modifications.

---

### V2_8045_Stable

Stable firmware tuned for 8×4.5 propellers.

Characteristics:

- Smooth hover
- Stable auto-level
- Well-balanced PID values
- Used as the reference firmware

---

### V3_1045_Final

Firmware tuned specifically for:

- F450 Frame
- A2212 1000KV Motors
- 30A ESCs
- 3S LiPo Battery
- 10×4.5 Propellers

Improvements:

- Reduced oscillations during aggressive maneuvers
- Improved recovery after large pitch and roll commands
- ESCs calibrated together
- Balanced propellers
- Stable hover
- Responsive controls
- Optimized PID tuning

---

## Final PID Values

| Parameter | Roll | Pitch | Yaw |
|-----------|------|-------|-----|
| P | 1.30 | 1.30 | 4.00 |
| I | 0.04 | 0.04 | 0.02 |
| D | 23.0 | 23.0 | 0.00 |

---

## Flight Test Results

Final 10×4.5 configuration achieved:

- ✅ Stable hover
- ✅ No oscillations during normal flight
- ✅ Smooth response to small stick inputs
- ✅ Stable medium stick maneuvers
- ✅ Controlled aggressive pitch and roll recovery
- ✅ Fast stabilization after stick release
- ✅ ESCs calibrated
- ✅ Propellers balanced

---

## Future Improvements

- Altitude Hold
- GPS Position Hold
- Return To Home
- Barometer Integration
- Magnetometer Integration
- Telemetry

---

## How to Flash

1. Clone this repository.
2. Open the required firmware version from the `Source` folder.
3. Open the `.ino` file in the Arduino IDE.
4. Select **Arduino Uno**.
5. Upload the firmware.
6. Perform ESC calibration if required.
7. Verify receiver channel mapping.
8. Remove propellers before first power-up.
9. Test hover in an open area before aggressive flight.

## Credits

### Original Project

- **Joop Brokking** — Creator of the original YMFC-AL Flight Controller.

### Engineering Contributions


Pahul Sodhi & Parmeet Singh – Stable 8×4.5 Configuration
    • Problem
    • Investigation
    • Solution
    • Result

Pahul Sodhi & Parmeet Singh – Stable 10×4.5 Configuration
    • Initial Problems
    • Investigation
    • Mechanical Improvements
    • PID Optimisation
    • Final Improvements