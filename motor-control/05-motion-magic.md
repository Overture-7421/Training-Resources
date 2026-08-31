# Motion Magic

**Applies to:** FRC only
**Supervision:** mentor required — real hardware
**Prerequisites:** [Position with an External Encoder](04-external-encoder.md)
**Concepts:** motion profiling, cruise velocity, acceleration, profiled vs. raw position control, smoothness.

A plain position loop gets a setpoint and goes as hard as it can until it gets there. That's fast, ugly, and hard on the robot.

Motion Magic puts a **planned path** in front of the controller: speed up at a chosen rate, hold a chosen speed, slow down in time to arrive gently. The mechanism ends up in the same place, but the trip is controlled instead of violent.

This is the last exercise in the set and it only makes sense once the previous ones work.

## Task

Use the same mechanism as the last two exercises, with tuning you already trust.

1. Command a large position change with the plain position loop from before. Watch how it starts and how it stops. Record how long it takes.
2. Switch the same mechanism to a profiled move. Set a cruise velocity and an acceleration that are conservative — well under what the mechanism can do.
3. Command the same move and compare. It should look deliberate rather than thrown.
4. Raise the cruise velocity in steps until the motion is as quick as it can be while still arriving cleanly.
5. Raise the acceleration separately. Notice these two do different things and shouldn't be tuned at the same time.
6. Find the point where the profile asks for more than the mechanism can deliver, and see what falling behind looks like.
7. Settle on values the team is willing to run on a real field, then write down why those numbers.

## Stretch

- Time the same move under both approaches and see how little you actually gave up for the smoothness.
- Command a very short move and check whether the mechanism ever reaches cruise velocity.
- Test with a fresh battery and a tired one, and see which parameter suffers first.
- Graph target position against actual through the whole move and read where they diverge.

## Watch for

- **Expecting it to fix bad tuning.** It won't. A profile on top of a loop that can't hold position is a smoother way to be wrong. If the previous exercises aren't solid, go back.
- **Cruise velocity set higher than the mechanism can reach.** The profile silently becomes a plain position move again, and students conclude the feature does nothing.
- **Tuning the profile and the gains at the same time.** Two variables, one observation, no conclusions. Change one thing at a time.
- Numbers copied from another team's robot. Different gearing, different mass, different answer. The numbers have to come from this mechanism.
- Treating "it looks smooth" as tuned. Ask what happens under a game piece's weight, or against a defender.
- Forgetting this is still the same underlying loop. When it misbehaves, the answer is usually in exercise 3 or 4, not here.

---

[← External Encoder](04-external-encoder.md) · [Index](../README.md)
