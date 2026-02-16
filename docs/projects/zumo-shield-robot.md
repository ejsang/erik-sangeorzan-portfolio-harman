# Zumo Shield Robot Navigation (C)

**Summary:** STM32-based robot navigation project showing motor control, sensor IO, PWM, timers, and UART telemetry using the STM32 HAL and C.

**Problem:** Implement reliable line-following and navigation on a Zumo robot using the STM32 microcontroller.

**Approach:** Use STM32 HAL to manage PWM motor control, GPIO sensors, timers and UART for debug telemetry; implement sensor scanning and corrective control logic in C.

**Results:** Working line-following implementation with telemetry and documented firmware (`main.c`).

---

### Skills demonstrated

- Embedded C programming on STM32 (PWM, timers, UART, GPIO)
- Low-level hardware control and real-time loop design for control systems
- Hardware debugging and interfacing with sensors and actuators

### Why this is relevant to HARMAN

- Demonstrates embedded firmware development, hardware driver use, and debugging.
- **UART telemetry** for debugging and **timing/PWM tuning** directly maps to device firmware development.

### Test Procedure

1. **Unit Test:** Verify individual sensor readings via UART output while manually moving the robot over contrasting surfaces.
2. **Integration Test:** Tune PID control loop parameters (Kp, Ki, Kd) using real-time telemetry to achieve stable line tracking at increasing speeds.
3. **System Validation:** Run full course navigation tests to verify corner handling and intersection logic.
