# Exercise 2 — Voltage Guard

**Category:** Syntax and control flow
**Prerequisites:** [Exercise 1](01-variables-and-types.md)

**Concepts:** `if` / `else if` / `else`, comparison operators, `&&`, `||`, `!`, nested conditions, `switch`.

## Part A — Battery status

Declare `double voltage`. Print a status based on these ranges:

| Voltage | Status |
|---------|--------|
| above 12.5 | GOOD |
| 11.5 to 12.5 | OK |
| 10.5 to 11.5 | LOW |
| below 10.5 | CRITICAL — stop driving |

Test it by editing the variable and re-running. Have them try the exact boundary values, `12.5` and `10.5`, and decide which branch *should* catch those.

## Part B — Combined rule

Add `boolean intakeRunning` and `boolean climbing`. Print a warning if voltage is below 11.5 **and** either mechanism is running. Then print a different message if voltage is fine **or** nothing is running.

## Part C — Power clamp

Declare `double requestedPower`. Motor power must stay between `-1.0` and `1.0`. If the requested value falls outside that range, replace it with the nearest limit and print a warning. Print the final power either way.

## Stretch

- Add a `String mode` variable (`"auto"`, `"teleop"`, `"test"`) and use a `switch` to print a different startup message for each. Include a `default`.
- Nest Part C inside Part A so the power limit drops to `0.5` when voltage is LOW.

## Watch for

- Writing four separate `if` statements instead of one `if / else if` chain, so multiple statuses print at once.
- `&` instead of `&&`. It compiles. It's a different operator.
- Comparing doubles with `==`. Show them `System.out.println(0.1 + 0.2 == 0.3);` and let the `false` land. Exercise 5 fixes this properly.
- Forgetting `break` in a `switch`.

---

[← Exercise 1](01-variables-and-types.md) · [Index](../README.md) · [Exercise 3 →](03-loops.md)
