# Open Loop Motor Control

**Applies to:** FTC and FRC
**Supervision:** mentor required — real hardware
**Prerequisites:** Programming Best Practices presentation
**Concepts:** percent output, voltage vs. power, motor direction, inversion, brake vs. coast.

> ⚠️ **A mentor must be present for this exercise.** It moves real hardware. Nobody powers a mechanism without a mentor in the room, and nobody runs it alone to get ahead.

The simplest thing a robot does: make a motor spin because you told it to. No sensors, no feedback. You ask for 40% and the motor gives you roughly 40% of whatever it has left in the battery — which is why this is called open loop. Nothing is checking the result.

## Task

Put the robot on blocks so the wheels are off the ground. Do this before writing anything.

1. Configure one motor and give it a fixed power. Start low — 20%. Confirm it spins.
2. Reverse it by commanding a negative power. Confirm it spins the other way.
3. Decide which direction counts as "forward" for this mechanism, and set the motor's inversion in configuration so a positive command always means forward. Don't do this by negating the number everywhere you call it.
4. Do the same for a second motor mounted the opposite way, so that both move the robot forward on a positive command.
5. Set brake mode and coast mode, and feel the difference when you cut power.

## Stretch

- Ramp the power up gradually instead of jumping straight to the target, and notice how much less the battery sags.
- Command the same power with a fresh battery and a low one. Same number, different speed. That's the limitation this whole section exists to solve.
- Read the current draw while stalling the mechanism briefly. Understand why nobody leaves a motor stalled.

## Watch for

- **Robot on the ground.** Somebody will forget. Blocks first, every time.
- **Full power as a first test.** Start at 20%. A mechanism at 100% with an inverted motor breaks itself before anyone reaches the disable button.
- **Negating the command instead of inverting the motor.** It works until someone else calls the same method and gets the opposite result. Set inversion in one place, in configuration.
- **Wrong motor ID.** A motor that doesn't move is usually addressed wrong, not broken. Check the ID before touching the code.
- Confusing power with speed. Same command, different battery, different speed. Beginners assume power sets speed and are surprised for the rest of the season if nobody corrects it here.
- Brownouts from spinning several motors at once on a tired battery.

---

[Index](../README.md) · [Velocity Control →](02-velocity-pid.md)
