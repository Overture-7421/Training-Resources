# Exercise 5 — Method Toolbox

**Category:** Data and methods
**Prerequisites:** [Exercise 4](04-arrays.md)

**Concepts:** `static` methods, parameters, return values, `void` vs. returning, scope, overloading, decomposition.

This exercise rewrites the previous two. Nothing new gets invented, which is the point: methods are for organizing code you already have.

## Task

Write these as `static` methods above `main`, then call them from `main`:

```java
static double clamp(double value, double min, double max)
static String batteryStatus(double voltage)
static double average(double[] values)
static int indexOfMax(double[] values)
static void printBanner(String text)
```

`main` should shrink to a short list of calls that exercises each one. That contrast, a long `main` before and a short `main` after, is the whole lesson.

## Stretch

- **Overload** `clamp` with a one-argument version, `clamp(double value)`, that assumes `-1.0` to `1.0` and calls the three-argument version.
- Write `static double deadband(double input, double threshold)` returning `0.0` when the input's magnitude is under the threshold, and the input otherwise. This is a real thing every driver-control loop does with joystick noise.
- Write `static boolean isNear(double a, double b, double tolerance)`. Point back to the broken `0.1 + 0.2 == 0.3` from Exercise 2 and show that this is the fix.

## Watch for

- Forgetting `static`, then getting a confusing "non-static method cannot be referenced from a static context" error. Explain it as a placeholder for now; Exercise 6 is where it actually makes sense.
- **Printing instead of returning.** This is the big one. If a student writes `System.out.println(avg);` inside `average()` and returns nothing, ask: does this method *print* the answer or *hand it back*? Only one of those lets you use the result in another calculation.
- Not returning on every branch of an `if`.
- Trying to use a variable declared inside a method from somewhere else. Good, concrete introduction to scope.

## Before moving on

Students now have a file full of loose `static` methods that all pass the same data back and forth. That's the setup for the next section. Ask them:

> These methods all work on the same robot. Why do we keep handing the robot's data to every single one?

Let them sit with it. Exercise 6 is the answer.

---

[← Exercise 4](04-arrays.md) · [Index](../../README.md) · [Exercise 6 →](../03-oop/06-classes-and-objects.md)
