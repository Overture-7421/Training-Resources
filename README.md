# Overture Training Resources

Training material for Overture team members, from first line of code to a working competition robot.

## The program

Our school is three years. The team's season structure follows it:

| Year | Program |
|------|---------|
| 1 | FTC |
| 2 | FRC |
| 3 | FRC |

Most members start in year 1 and go through everything in order. Members who join in year 2 skip FTC entirely — they do the Java and GitHub tracks, then go straight to FRC.

## How this is run

**Work through this with a mentor, at the pace the mentor sets.** Don't jump ahead on your own.

That isn't about gatekeeping. Several exercises assume a presentation you haven't seen yet — the slides come first and the exercise is the practice that follows. Starting an exercise cold means fighting concepts nobody has explained to you, which is slower than waiting and a lot more discouraging.

So:

- A mentor says when a track or an exercise starts. Ask before moving on.
- If a presentation is listed for a topic, it happens before the exercise, not after.
- Finishing first isn't the goal. If you're ahead, the stretch goals are there for exactly that.
- Getting stuck is normal and expected. Say so early rather than grinding alone.

Mentors: the order is fixed, but the pace isn't. Hold the group where it needs holding.

## Tracks

Work through these in order. Each one assumes the ones before it.

| # | Track | What it covers | Status |
|---|-------|----------------|--------|
| 1 | [Java](java-training/README.md) | Variables through inheritance and polymorphism. Plain JDK, no FIRST libraries. | 8 exercises, done |
| 2 | [Git and GitHub](github-training/README.md) | Commits, push and pull, branches, pull requests. Enough to work on a shared robot repo without stepping on each other. | 4 exercises, done |
| 3 | FTC | The FTC SDK, OpModes, hardware mapping, a first driving robot. | not started |
| 4 | FRC | WPILib, command-based, subsystems, a first driving robot. | not started |
| 5 | Control theory | PID, feedforward, motion profiling. Split in two: an FTC-level pass and a deeper FRC-level pass. | not started |

**Control theory is the one track you come back to.** The FTC pass covers enough to make a mechanism hold a position. The FRC pass goes back over the same ground with the math and the tuning process. Doing the first pass does not mean you're done with it.

## Two paths through

**Joining in year 1**

```
Java → GitHub → FTC → Control theory (FTC pass)
     then, year 2:
     FRC → Control theory (FRC pass)
```

**Joining in year 2**

```
Java → GitHub → FRC → Control theory (FRC pass)
```

Someone joining in year 2 who already writes Java starts at GitHub.

## A note on sources

Some material here is borrowed from other teams while we write our own. Anything borrowed is credited in the file that uses it. If you add borrowed material, credit it there too.

## Status

The Java and GitHub tracks are written. FTC, FRC, and control theory are planned but unwritten. Some material is borrowed from other teams for now — see the note above. We're building an app to track member progress through all of this; until it exists, this repo is where the material lives.
