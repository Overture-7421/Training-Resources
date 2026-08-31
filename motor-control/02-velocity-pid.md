# Velocity Control with PID and Feedforward

**Applies to:** FTC and FRC
**Supervision:** mentor required — real hardware
**Prerequisites:** [Open Loop Motor Control](01-open-loop.md), Control Loops presentation
**Concepts:** closed loop control, internal encoder, velocity units, feedforward, proportional gain, steady-state error.

> ⚠️ **A mentor must be present for this exercise.** It moves real hardware. Nobody powers a mechanism without a mentor in the room, and nobody runs it alone to get ahead.

The previous exercise asked for power and hoped. This one asks for a **speed** and corrects itself until it gets there. The motor's built-in encoder reports how fast it's actually turning, and the controller closes the gap.

Feedforward comes first and does most of the work: it's the estimate of what power this speed normally needs. PID only cleans up the difference.

## Task

Robot on blocks again.

1. Read the motor's internal encoder and display the actual velocity while commanding a fixed power. Confirm the number moves and makes sense before trusting it for anything.
2. Write down what units you're reading. Do this explicitly — it is the single most common source of confusion in this exercise.
3. Command a target velocity using feedforward only. Tune it until the motor lands near the target on its own.
4. Add proportional gain until the remaining error closes. Command several different speeds and check each one.
5. Display commanded velocity next to actual velocity. Watch the gap while the mechanism spins up.
6. Load the mechanism by hand, briefly and safely, and watch the controller push back to hold speed. That recovery is the whole point of closed loop.

## Stretch

- Tune to hold speed with a nearly dead battery, and confirm the same target still works.
- Add integral gain and find the setpoint where it helps. Then find where it makes things worse.
- Graph commanded against actual over time and read the shape.
- Command a step change from slow to fast and measure how long it takes to settle.

## Watch for

- **Tuning P before feedforward.** Backwards, and it produces a loop that oscillates and never quite arrives. Feedforward first, always.
- **Units.** Rotations per second, RPM, or encoder ticks per time interval, depending on the vendor and the API. A gain tuned in the wrong units is off by a factor of hundreds and looks like broken code. Make them state the units out loud.
- **Gear ratio.** The encoder reads the motor shaft, not the mechanism. If the numbers are off by a constant factor, this is why.
- **Cranking P until it oscillates**, then leaving it there. Loud and shaky is not tuned.
- Testing on blocks and assuming it will behave the same under load. It won't. Say so now.
- Expecting instant response. Every mechanism takes time to spin up, and no amount of gain removes physics.

---

[← Open Loop](01-open-loop.md) · [Index](../README.md) · [Position Control →](03-position-pid.md)
