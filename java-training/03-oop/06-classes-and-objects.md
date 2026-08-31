# Exercise 6 — Your First Class: Motor

**Category:** OOP
**Prerequisites:** [Exercise 5](../02-data-and-methods/05-methods.md)

**Concepts:** `class`, instance fields, constructor, `this`, instance methods, `new`, dot notation, `toString()`, one class per file.

## Task

Two files this time, in the same folder.

**`Motor.java`** — no `main` method. This file only describes what a motor *is*.

- Fields: `String name`, `int port`, `double power`
- Constructor: `Motor(String name, int port)` that stores both and sets `power` to `0.0`
- Methods: `setPower(double newPower)`, `stop()`, `getPower()`, `describe()`

**`Robot.java`** — has `main`. Create three motors, drive them, print them:

```java
Motor leftFront  = new Motor("Left Front", 1);
Motor rightFront = new Motor("Right Front", 2);
Motor intake     = new Motor("Intake", 3);

leftFront.setPower(0.6);
rightFront.setPower(-0.6);
intake.setPower(1.0);

leftFront.describe();
rightFront.describe();
intake.describe();
```

## The point

Three objects, one class, three completely independent sets of values. `leftFront.power` and `intake.power` are different numbers living in different places in memory. Draw three boxes on the whiteboard. This is the thing Exercise 5 couldn't do without passing everything around by hand.

## Stretch

- Move the `clamp` logic from Exercise 5 *inside* `setPower`, so a motor can't be set out of range no matter who calls it.
- Replace `describe()` with an overridden `toString()`, then `System.out.println(leftFront)` directly. Explain that `println` calls `toString()` for you.
- Add `boolean isMoving()` using the `isNear` idea from Exercise 5.

## Watch for

- Forgetting `new`. `Motor m;` then `m.setPower(0.5)` gives a NullPointerException. The variable exists; the object doesn't.
- Writing `void Motor(String name, int port)`. Adding a return type turns a constructor into an ordinary method, and the resulting error is baffling. Constructors have no return type and match the class name exactly.
- Shadowing: a parameter named `name` and a field named `name`, then writing `name = name`. This is the moment `this` earns its keep.
- File name must match the public class name, exactly, capitalization included.
- Putting `main` inside `Motor.java`. Keep the "what it is" file separate from the "run it" file.

---

[← Exercise 5](../02-data-and-methods/05-methods.md) · [Index](../../README.md) · [Exercise 7 →](07-encapsulation-and-composition.md)
