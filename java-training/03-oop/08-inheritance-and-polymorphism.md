# Exercise 8 — Inheritance and Polymorphism: Subsystems

**Category:** OOP
**Prerequisites:** [Exercise 7](07-encapsulation-and-composition.md)

**Concepts:** `extends`, `super`, `@Override`, abstract classes, overriding vs. overloading, polymorphism, interfaces.

This is the payoff exercise. Everything lands here.

## Part A — A common shape

**`Subsystem.java`**, an abstract class:

- `protected String name`
- constructor taking the name
- concrete `getName()`
- `public abstract void periodic();`
- `public abstract void stop();`

## Part B — Three of them

- `Drivetrain extends Subsystem` (already written, just adapt it)
- `Intake extends Subsystem` with a `boolean running` and a `toggle()` method
- `Arm extends Subsystem` with a `double angle` and `moveTo(double target)`

Each one calls `super(name)` and provides its own `periodic()` and `stop()`. Every override gets an `@Override` annotation.

## Part C — The whole point

In `Robot.java`:

```java
Subsystem[] subsystems = {
    new Drivetrain(1, 2, 3, 4),
    new Intake("Intake", 5),
    new Arm("Arm", 6)
};

for (int cycle = 0; cycle < 10; cycle++) {
    for (Subsystem s : subsystems) {
        s.periodic();
    }
}
```

One loop. Three different behaviors. Not a single `if` checking what type anything is. The array is declared as `Subsystem[]` and Java figures out at runtime which `periodic()` to call.

Then tell them: a real robot program runs a loop like that fifty times a second, and it's the reason WPILib and the FTC SDK are shaped the way they are. When they open a real project, they'll recognize the skeleton.

## Stretch

- Write an `interface Loggable` with `String getStatus()`. Implement it on `Arm` and `Intake` but not `Drivetrain`. Loop over the subsystems with `instanceof` to log only the ones that support it, then discuss why a shared interface beats scattering type checks around.
- Override `toString()` once in `Subsystem` and confirm all three subclasses inherit it.
- Delete a `super(name)` call and read the compiler error together.
- Have `Arm.periodic()` call `super.periodic()` first, if you gave `Subsystem` a concrete version.

## Watch for

- **Overriding vs. overloading.** A student writes `periodic(int x)` in a subclass, no override happens, the parent version runs, and nothing looks wrong. `@Override` turns that silent bug into a compiler error. Require it on every override, every time. This is the single most valuable habit in the whole set.
- `super(...)` must be the first statement in a subclass constructor.
- Trying to `new Subsystem(...)` on an abstract class.
- "Where is that method defined?" Trace the chain out loud until they can do it themselves.
- Deep inheritance trees. Two levels is plenty. When a student wants a third, ask whether composition from Exercise 7 would do the job better. Usually it would.

---

[← Exercise 7](07-encapsulation-and-composition.md) · [Index](../../README.md)
