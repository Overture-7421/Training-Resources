# Exercise 4 — Sensor Log

**Category:** Data and methods
**Prerequisites:** [Exercise 3](../01-syntax-and-control-flow/03-loops.md)

**Concepts:** array declaration and initialization, `.length`, indexing, `for` vs. enhanced `for`, min/max/sum/average, tracking an index.

## Task

Start with this array of distance sensor readings, in inches:

```java
double[] distances = {24.5, 23.8, 24.1, 60.2, 23.9, 24.0,
                      24.3, 12.7, 24.2, 23.7, 24.4, 24.1};
```

Compute and print:

1. How many readings there are (use `.length`, don't count by hand)
2. The sum and the average
3. The largest and smallest reading
4. The **index** of the largest reading
5. How many readings fall below 20.0 inches

## Stretch

- Print the array twice: once with a counted `for` loop showing indexes, once with an enhanced `for` loop. Ask when each is the right choice. (Answer: you need the counted loop for #4.)
- Reverse the array in place, without creating a second array.
- Add a 2D array `int[][] scores = new int[3][4]` for 3 matches by 4 scoring categories. Fill it and print a total per match.

## Watch for

- `i <= array.length` causing `ArrayIndexOutOfBoundsException`. Almost guaranteed. Let it happen, then read the error message together.
- `array.length` (no parentheses) vs. `string.length()` (with parentheses). Inconsistent, annoying, worth calling out.
- Initializing `min` to `0`. The minimum then comes out as `0`, which isn't in the array. Initialize to `distances[0]` instead.
- Trying to change an array's size after creating it.

---

[← Exercise 3](../01-syntax-and-control-flow/03-loops.md) · [Index](../README.md) · [Exercise 5 →](05-methods.md)
