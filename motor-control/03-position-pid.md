# Position Control with PID

**Applies to:** FTC and FRC
**Supervision:** mentor required — real hardware
**Prerequisites:** [Velocity Control with PID and Feedforward](02-velocity-pid.md)
**Concepts:** position vs. velocity control, setpoint, error, zeroing, tolerance, holding against load.

> ⚠️ **A mentor must be present for this exercise.** It moves real hardware. Nobody powers a mechanism without a mentor in the room, and nobody runs it alone to get ahead.

Same encoder, same controller, different question. Velocity control asks "how fast." Position control asks "where," and then holds there while something tries to push it away.

Use a mechanism that has somewhere to go and somewhere to stop — an arm or a turret, not a drivetrain wheel.

## Task

Robot on blocks or the mechanism clear of anything it could hit. Know where the hard stops are before powering anything.

1. Find the mechanism's range of travel by hand, with the robot off. Write down the safe limits.
2. Zero the encoder at a known physical position. Decide what that position means and be consistent about it.
3. Display the current position continuously and move the mechanism by hand. Confirm the number changes in the direction you expect, and that it matches reality.
4. Command a small move to a nearby setpoint. Small first — a large step on an untuned loop slams the mechanism.
5. Tune until it arrives without overshooting into a hard stop or oscillating around the target.
6. Command several setpoints across the range and confirm each one.
7. Push gently against the mechanism and watch it hold position. That resistance is closed loop position control.
8. Add a tolerance so the code can say when it has arrived, and stop treating "close enough" as a number someone eyeballs.

## Stretch

- Add software limits so a bad setpoint can't drive into a hard stop.
- Hold a position against gravity, and work out why some mechanisms need constant effort to stay still while others don't.
- Move to a setpoint, cut power mid-travel, then re-enable, and watch it resume.
- Compare how the same gains behave with the mechanism loaded and unloaded.

## Watch for

- **Not zeroing, or zeroing in a different place each run.** Every setpoint is then meaningless. This is the most common failure here.
- **Testing with a big step first.** The mechanism reaches full speed and hits the hard stop. Small moves until the tuning is trusted.
- **Hard stops.** Know where they are before powering on. A position loop will happily drive into one and keep pushing.
- **Integral windup** on a mechanism that can't reach its target — the output climbs and climbs and then the mechanism lunges. Show it once on purpose, with a hand holding the mechanism back.
- Oscillating around the setpoint and calling it done. Buzzing is not holding.
- Gear ratio again. The encoder reads the motor, the setpoint is about the mechanism.
- Forgetting the mechanism falls when disabled. Brake mode and gravity both matter here.

---

[← Velocity Control](02-velocity-pid.md) · [Index](../README.md) · [External Encoder →](04-external-encoder.md)
