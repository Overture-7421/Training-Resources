# Exercise 7 — Encapsulation and Composition: Drivetrain

**Category:** OOP
**Prerequisites:** [Exercise 6](06-classes-and-objects.md)

**Concepts:** `private`, getters and setters, validation, constructor overloading, `this(...)`, `static` vs. instance members, `final`, objects that contain other objects, arrays of objects.

Continues the project from Exercise 6.

## Part A — Lock the doors

Make every field in `Motor` `private`. `Robot.java` will stop compiling anywhere it touched a field directly. That's the feature, not the bug.

Add getters. Add setters **only where changing the value actually makes sense**, and put real validation inside them:

- `setPower` clamps to `-1.0 … 1.0`
- there is no `setPort`, because a motor doesn't move to a different port at runtime. Make `port` `private final`.

Ask them: what could go wrong if any code anywhere could write `motor.power = 47.0`?

## Part B — Static vs. instance

Add a `private static int motorCount` that increments in the constructor, plus `public static int getMotorCount()`.

Call it as `Motor.getMotorCount()`, not `leftFront.getMotorCount()`. `power` belongs to *a motor*. `motorCount` belongs to *the class*. That contrast is the cleanest explanation of `static` they'll get.

## Part C — Build a bigger thing out of smaller things

**`Drivetrain.java`** holds four `Motor` objects as fields (or a `Motor[]`).

- Constructor takes four port numbers and creates the four motors
- `arcadeDrive(double forward, double turn)` computes left and right power and calls `setPower` on each motor
- `stop()` stops all four

`Robot.java` now shrinks to something like:

```java
Drivetrain drive = new Drivetrain(1, 2, 3, 4);
drive.arcadeDrive(0.5, 0.2);
drive.stop();
```

A Drivetrain *has* Motors. That's composition, and it's the workhorse of real robot code.

## Stretch

- Overload the constructor: add a no-argument `Drivetrain()` that uses default ports by calling `this(1, 2, 3, 4)` on its first line.
- Store the motors as a `Motor[]` and loop over them in `stop()`. Note that `new Motor[4]` gives four nulls, not four motors.
- Add a `Drivetrain` field `private final String name`, set in the constructor, with a getter and no setter.

## Watch for

- Reflexively generating a getter and setter for every field. Ask each time whether outside code has any business changing that value. Most of the time it doesn't.
- A setter that assigns without validating is just a public field with extra steps. The clamp has to be real.
- Using `this` inside a `static` method. There's no object to point at.
- `new Motor[4]` then immediately calling a method on element 0. It's an array of object *references*, all null until each one is assigned.

> **Don't stop mid-exercise.** Part A intentionally breaks the build until Part C is done. Finishing this in one session matters more than it does elsewhere.

---

[← Exercise 6](06-classes-and-objects.md) · [Index](../../README.md) · [Exercise 8 →](08-inheritance-and-polymorphism.md)
