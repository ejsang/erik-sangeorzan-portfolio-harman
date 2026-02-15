```markdown
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

- Demonstrates embedded firmware development fundamentals: hardware driver usage, PWM/timing control, and real-time control loops—all essential for automotive embedded systems.
- UART telemetry debugging and hardware profiling skills transfer directly to embedded audio systems development.

### Test Procedure

1. **Unit Test:** Verify individual sensor readings via UART output while manually moving the robot over contrasting surfaces.
2. **Integration Test:** Tune PID control loop parameters (Kp, Ki, Kd) using real-time telemetry to achieve stable line tracking at increasing speeds.
3. **System Validation:** Run full course navigation tests to verify corner handling and intersection logic.

### How to run / reproduce

- Open the `Line follower` project in STM32CubeIDE (the project was created with STM32 Cube tools).
- Build and flash the firmware to the STM32 (Zumo) board.
- Open a serial console to the board (LPUART1 at 115200 baud) to view `printf` telemetry and debug messages.
- Verify motor and sensor wiring matches pins in `main.c`; adjust PWM/drive parameters as needed and test in a controlled environment.

### Downloads & presentation video

- [Line follower code (zip)](../assets/zumo-shield-robot/zumo-line-follower.zip){:target="_blank"}
- **[Presentation video](https://youtu.be/iPAF4b1J8Rs){:target="_blank"}**

### What to inspect

- Open `main.c` in the zip and inspect the sensor scan and correction logic; this is where hardware timing and PWM control are implemented.
```