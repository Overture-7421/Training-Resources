# Java Training

Track 1 of 5. See the [curriculum index](../README.md) for how this fits with the rest.

Eight exercises taking new team members from their first variable to a working object-oriented robot program. Written for FRC/FTC students with little or no programming background.

Nothing in here uses WPILib, the FTC SDK, or any FIRST library. It's plain Java, run from an IDE or the command line. The exercises borrow robotics *situations* (battery voltage, motor power, sensor readings) but no robotics *code*, so the vocabulary is already familiar when students open the real SDK later.

## Exercises

| # | Exercise | Category |
|---|----------|----------|
| 1 | [Robot Stats Card](01-syntax-and-control-flow/01-variables-and-types.md) | Syntax & control flow |
| 2 | [Voltage Guard](01-syntax-and-control-flow/02-conditionals.md) | Syntax & control flow |
| 3 | [Loop Drills](01-syntax-and-control-flow/03-loops.md) | Syntax & control flow |
| 4 | [Sensor Log](02-data-and-methods/04-arrays.md) | Data & methods |
| 5 | [Method Toolbox](02-data-and-methods/05-methods.md) | Data & methods |
| 6 | [Your First Class](03-oop/06-classes-and-objects.md) | OOP |
| 7 | [Encapsulation & Composition](03-oop/07-encapsulation-and-composition.md) | OOP |
| 8 | [Inheritance & Polymorphism](03-oop/08-inheritance-and-polymorphism.md) | OOP |

**Order matters.** Each exercise assumes the one before it.

**A mentor sets the pace.** Don't start an exercise before your mentor says to — some of them have a presentation that comes first. See [How this is run](../README.md#how-this-is-run).

## Layout

```
01-syntax-and-control-flow/   variables, types, branching, iteration
02-data-and-methods/          arrays, and breaking code into reusable pieces
03-oop/                       classes, encapsulation, inheritance
presentations/                slides for the front of the room
```

The [presentations](presentations/README.md) are borrowed from another team for now, pending our own.

Every exercise file has the same shape: concepts, task, stretch goals, and a **Watch for** section listing the specific bugs beginners hit. That last section is written for whoever is teaching, not for the student.

## How to run

Exercises 1–5 are each a single file with a single `main` method:

```
javac RobotStats.java
java RobotStats
```

Exercises 6–8 use several files in one folder. Compile them all, then run only the one that has `main`:

```
javac *.java
java Robot
```

IntelliJ and VS Code handle both cases if you just hit run.

## Notes for whoever is teaching

**Input.** None of these use `Scanner`. Robot code never reads from a keyboard, so students should get comfortable editing hardcoded values and re-running instead. If you want to teach `Scanner` anyway, bolt it onto Exercise 2.

**Pacing.** Plan on several sessions, not a weekend. Exercises 1–3 move fast and can be doubled up. Exercises 5 and 8 need the most room; don't rush either. Let students finish at their own speed — that's what the stretch goals are for.

**Stopping points.** Safe places to break are after Exercise 4 and after Exercise 6. Stopping partway through 7 leaves students with half-encapsulated code that doesn't compile, which is a bad state to leave them in for a week.

**Stretch goals** exist so the students who finish in twenty minutes have somewhere to go while everyone else catches up. Nobody needs to do all of them.

**Continuity.** Exercises 6–8 are one continuous project, not three separate ones. Students keep extending the same files.

**Slides come first.** The decks in [presentations/](presentations/README.md) are borrowed and don't map one to one onto the exercises. Where a deck covers a topic, present it before the matching exercise — the exercise is practice, not the introduction. The exercises are still the spine of the track.

**Hold the group.** Students shouldn't work ahead on their own. Someone who reads Exercise 6 before the classes presentation will spend the session confused about syntax instead of learning the idea. Point fast finishers at the stretch goals instead.

## Next

When students finish Exercise 8, they move to the [GitHub track](../github-training/README.md). Members who joined in year 2 go GitHub, then straight to FRC.

[← Curriculum index](../README.md)
