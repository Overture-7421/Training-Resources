# Exercise 3 — Loop Drills

**Category:** Syntax and control flow
**Prerequisites:** [Exercise 2](02-conditionals.md)

**Concepts:** `for`, `while`, `do-while`, the accumulator pattern, counters, `break`, `continue`, nested loops.

Four short parts in one file. Each is a few lines.

## Part A — Countdown

Print `10` down to `1`, one per line, then `GO!`.

## Part B — Accumulator

Use a loop to add up every number from 1 to 100 and print the total. Do not use a formula. The point is the accumulator pattern: a variable declared *before* the loop that grows *inside* it.

## Part C — Multiplication table

Nested loops printing a 12 × 12 table. Use `printf` with a width specifier like `%4d` so the columns line up.

## Part D — Ramp

Start at `0.0` power. Using a `while` loop, increase by `0.05` each pass and print the value until it reaches `1.0`. This is a simplified version of a real ramp-rate limiter.

## Stretch

- In Part A, skip every odd number using `continue`.
- In Part B, `break` out as soon as the running total passes 500 and print which number got you there.
- Rewrite Part D as a `for` loop. Discuss which reads better and why.

## Watch for

- Off-by-one. `i <= 10` vs. `i < 10` deserves five minutes of its own.
- Infinite `while` loops from a missing increment. Teach `Ctrl+C` early.
- Part D drifting: after 20 additions of `0.05` you may not land exactly on `1.0`. If a student hits this, they've discovered floating point error on their own, which is the best way to meet it. Loop on a counter instead of the accumulated double.
- Declaring the accumulator *inside* the loop, resetting it every pass.

---

[← Exercise 2](02-conditionals.md) · [Index](../../README.md) · [Exercise 4 →](../02-data-and-methods/04-arrays.md)
