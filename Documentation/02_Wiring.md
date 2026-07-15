# Wiring

This document describes the electrical connections used in the YMFC-AL Flight Controller project.

---

# Flight Controller

- Arduino r3
- MPU6050 Gyroscope & Accelerometer
- FlySky FS-iA6B Receiver
- 4 × 30A ESCs
- 4 × A2212 1000KV Brushless Motors

---

# MPU6050 Connections

| MPU6050 | Arduino Nano |
|----------|--------------|
| VCC | 5V |
| GND | GND |
| SDA | A4 |
| SCL | A5 |

---

# Receiver Connections

| Receiver Channel | Arduino Pin | Function |
|------------------|-------------|----------|
| CH1 | D8 | Roll |
| CH2 | D9 | Pitch |
| CH3 | D10 | Throttle |
| CH4 | D11 | Yaw |

---

# ESC Connections

| ESC | Arduino Pin | Motor Position |
|-----|-------------|----------------|
| ESC1 | D4 | Front Right |
| ESC2 | D5 | Rear Right |
| ESC3 | D6 | Rear Left |
| ESC4 | D7 | Front Left |

---

# Power Distribution

- 3S LiPo Battery
- XT60 Connector
- Power Distribution Board
- 30A ESCs

---

# Motor Layout

Motor 1 → Front Right

Motor 2 → Rear Right

Motor 3 → Rear Left

Motor 4 → Front Left

---

# Propeller Rotation

Motor 1 → Clockwise (CW)

Motor 2 → Counter Clockwise (CCW)

Motor 3 → Clockwise (CW)

Motor 4 → Counter Clockwise (CCW)

---

# Images

The following images will be added:

- Complete wiring diagram
- Receiver wiring
- MPU6050 wiring
- ESC wiring
- Final assembled electronics