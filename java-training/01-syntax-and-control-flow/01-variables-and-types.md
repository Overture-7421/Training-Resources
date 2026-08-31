# Exercise 1 — Robot Stats Card

**Category:** Syntax and control flow
**Prerequisites:** the [Java Fundamentals deck](https://docs.google.com/presentation/d/1MxjAYEkdW9MVuQUSKM9xFdQ3vQl-1MXcdd2jdfOI_KY/edit?usp=sharing), presented first.

**Concepts:** `int`, `double`, `boolean`, `String`, `char`, declaration vs. assignment, arithmetic operators, integer division, `println` vs. `printf`, comments, `final`.

## Task

Create `RobotStats.java`. Inside `main`, declare variables describing a robot:

- name (String)
- weight in pounds (double)
- number of motors (int)
- whether it passed inspection (boolean)
- drivetrain code letter, like `'T'` for tank (char)

Then compute the weight in kilograms and print a formatted stat card.

### Sample output

```
=== ROBOT STATS ===
Name:        Gearbox
Weight:      114.50 lb (51.93 kg)
Motors:      8
Drivetrain:  T
Inspected:   true
```

## Stretch

- Store the lb-to-kg conversion factor in a `final double` constant instead of typing `2.205` inline. Ask why that's better.
- Print the average weight carried per motor, to two decimals.
- Add a variable for match time in seconds (150) and print it as minutes and seconds using `/` and `%`.

## Watch for

- `int / int` truncating. `150 / 60` is `2`, not `2.5`. This one bites everybody once.
- `=` (assign) vs. `==` (compare).
- `"Motors: " + 3 + 5` printing `35`. Good teaching moment about `+` doing two different jobs.
- Forgetting `%n` or `\n` at the end of a `printf`.

---

[Index](../../README.md) · [Exercise 2 →](02-conditionals.md)
