# Lessons Learned

This project provided valuable practical experience in embedded systems, control systems, sensor integration, and experimental engineering.

---

# Hardware Before Software

Many flight problems initially appeared to be software related but were actually caused by mechanical issues.

Balancing propellers, calibrating ESCs, and reducing vibration significantly improved controller performance before any PID changes were made.

---

# Debugging Is More Important Than Guessing

Instead of randomly modifying PID values, sensor data was analysed using the Arduino IDE Serial Monitor.

This approach made it possible to identify the true cause of several stability problems.

---

# One Change at a Time

Changing multiple parameters simultaneously makes it difficult to identify the effect of each modification.

Throughout this project only one major parameter was changed before every flight test.

---

# Mechanical Vibration Matters

Even small propeller imbalance produced measurable effects on MPU6050 readings.

Reducing vibration greatly simplified PID tuning.

---

# PID Tuning Requires Patience

Stable flight was achieved through many iterative flight tests rather than large parameter changes.

Small adjustments followed by repeated testing produced the best results.

---

# Documentation Is Engineering

Recording every modification, observation, and result made troubleshooting significantly easier.

Good documentation is as valuable as good code.

---

# Teamwork

The successful completion of this project was the result of continuous collaboration, discussion, experimentation, and flight testing.

Different ideas were evaluated, tested, and refined until a stable solution was achieved.

---

# Final Reflection

This project was much more than building a quadcopter.

It provided practical experience in:

- Embedded Systems
- Sensor Integration
- Control Systems
- Mechanical Optimization
- Experimental Engineering
- Systematic Debugging
- Flight Testing
- Open Source Development

The experience gained throughout this project forms a strong foundation for future work in autonomous systems, robotics, and UAV development.