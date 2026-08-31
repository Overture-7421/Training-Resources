# Position with an External Encoder

**Applies to:** FRC only
**Supervision:** mentor required — real hardware
**Prerequisites:** [Position Control with PID](03-position-pid.md)
**Concepts:** external vs. internal encoders, absolute vs. relative, sensor placement, gear ratio, offsets, backlash.

Until now the position came from inside the motor. That reading passes through the gearbox, the chain, and every bit of slop between the motor and the thing you actually care about. An external encoder mounted on the mechanism itself measures the real answer.

If it's an absolute encoder, it also knows where it is the moment the robot powers on — no zeroing routine, no driving to a limit switch before a match.

Position only here. Speed isn't the point.

## Task

1. Identify the sensor and where it's mounted. Say out loud what it's measuring and how that differs from the motor's internal encoder.
2. Read it and display the raw value. Move the mechanism by hand and confirm the number tracks.
3. Check the direction. If the sensor counts up while the motor's positive direction goes down, fix it in configuration now. Do not skip this step.
4. Set the offset so the mechanism's real zero reads as zero. Power cycle the robot and confirm it still reads correctly without moving anything.
5. Work out the ratio between sensor units and real mechanism units — degrees, or whatever the team actually talks in. Convert once, in one place.
6. Run the position loop from the external sensor instead of the internal one.
7. Compare the two readings across the range. Where they disagree is the slop the internal encoder can't see.

## Stretch

- Move the mechanism to a setpoint from above and from below, and measure the difference. That gap is backlash.
- Power cycle mid-travel and confirm the absolute sensor knows where it is immediately.
- Use the absolute sensor once at startup to seed the internal encoder, then run off the internal one.
- Unplug the sensor while running, safely, and decide what the code should do about a reading that stops updating.

## Watch for

- **Sensor direction opposite the motor.** The loop pushes the wrong way, error grows, and the mechanism accelerates into a hard stop. This is the dangerous failure in this exercise. Check direction before closing the loop, at low power, mentor's hand near disable.
- **Offset not saved, or set while the mechanism was somewhere else.** Everything is off by a constant and nobody notices until a match.
- **Ratio math done twice**, or done in two different files with different numbers. Convert in one place.
- Trusting a sensor mounted after the backlash. If it's on the far side of a chain, it reads the chain, not the mechanism.
- Wiring and CAN IDs. A sensor reading a frozen number is usually addressed or wired wrong, not broken.
- Assuming absolute means calibrated. It knows where it is; it doesn't know what you wanted zero to mean.

---

[← Position Control](03-position-pid.md) · [Index](../README.md) · [Motion Magic →](05-motion-magic.md)
