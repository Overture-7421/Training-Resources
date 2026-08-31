# Overture Training Resources

> Training for new Software team members, from first variable to a working robot program.
>
> A mixture of presentations given by mentors and exercises done on your own machine. **The order matters** — each resource builds on the ones before it.

## 1. How this works

**A mentor sets the pace.** Don't work ahead. Presentations come before the exercises they cover, and starting an exercise cold means fighting concepts nobody has explained yet.

**Proof of completion.** For presentations, register your attendance. For exercises, review the finished code with a mentor so they can check you understood it, not just that it runs.

**Getting stuck is expected.** Say so early instead of grinding alone. Finishing first isn't the goal — that's what stretch goals are for.

## 2. Order of completion

Our school is three years, and the season structure follows it: **year 1 is FTC, years 2 and 3 are FRC.**

Most members start at 1 and work down. Members who join in year 2 skip the FTC section — Java, Git, then straight to FRC. If they already write Java, they start at Git.

## 3. Resources

### Java

1. [W3Schools Java Tutorial](https://www.w3schools.com/java/) — **External** · self-study, done before anything else
2. [Java Fundamentals](https://docs.google.com/presentation/d/1MxjAYEkdW9MVuQUSKM9xFdQ3vQl-1MXcdd2jdfOI_KY/edit?usp=sharing) — **Presentation** · borrowed, Spectrum 3847 (C1.1) · replace by 2027
3. [Robot Stats Card](java-training/01-syntax-and-control-flow/01-variables-and-types.md) — **Exercise** · variables and types
4. [Voltage Guard](java-training/01-syntax-and-control-flow/02-conditionals.md) — **Exercise** · conditionals
5. [Loop Drills](java-training/01-syntax-and-control-flow/03-loops.md) — **Exercise** · loops
6. [Sensor Log](java-training/02-data-and-methods/04-arrays.md) — **Exercise** · arrays
7. [Method Toolbox](java-training/02-data-and-methods/05-methods.md) — **Exercise** · methods
8. [Your First Class](java-training/03-oop/06-classes-and-objects.md) — **Exercise** · classes and objects
9. [Encapsulation and Composition](java-training/03-oop/07-encapsulation-and-composition.md) — **Exercise** · privacy, getters, has-a
10. [Inheritance and Polymorphism](java-training/03-oop/08-inheritance-and-polymorphism.md) — **Exercise** · subsystems

Plain Java only — no WPILib, no FTC SDK. Items 8–10 are one continuous project, not three separate ones.

Items 3–7 are each a single file: `javac RobotStats.java`, then `java RobotStats`. Items 8–10 use several files in one folder: `javac *.java`, then `java Robot`. VS Code and IntelliJ handle both if you just hit run.

The eight exercises are tracked as **Java 1–8** on the progress sheet, matching their own headers rather than the numbers in this list.

### Git and GitHub

11. Version Control, Git and GitHub — **Presentation** · _not written yet_

Scope: commits, push and pull, branches, pull requests. Nothing more — rebase, cherry-pick, stash, and rewriting history aren't needed on a robot repo and are a good way to lose a beginner's work. Students work in VS Code, which has a terminal built in.

### FTC

12. Intro to FTC Controls — **Presentation** · _we don't have this yet_
13. [Intro to Vision Systems](https://docs.google.com/presentation/d/18Km6PWV-6Slt5ESQbFIYo8DxL3BhUzXH_tmMuM71YTA/edit?usp=sharing) — **Presentation** · borrowed, Spectrum 3847 (C1.6) · replace by 2027
14. Install FTC Software Tools — **Presentation** · _we don't have this yet_ · needed for 2026, then rewritten for the new control system in 2027
15. Beginner Motors for FTC — **Presentation** · _we don't have this yet_
16. Programming Best Practices — **Presentation** · _we don't have this yet_
17. Control Loops: PID and Motion Magic — **Presentation** · borrowed, CTRE · replace by 2027 · _link needed_
18. [Open Loop Motor Control](motor-control/01-open-loop.md) — **Exercise** · mentor supervised
19. [Velocity Control with PID and Feedforward](motor-control/02-velocity-pid.md) — **Exercise** · mentor supervised
20. [Position Control with PID](motor-control/03-position-pid.md) — **Exercise** · mentor supervised

**The FTC control system changes in 2027.** Anything here that describes specific hardware or the software that talks to it needs a 2026 version now and a rewrite for 2027 — that's a different deadline from the borrowed decks, which get replaced because they aren't ours, not because they go stale.

Items 13, 16 and 17 are **shared with FRC**, and so are exercises 18–20. They teach vision, control loops, good practice and motor control in general terms rather than for one program, so the same material serves both. Everything shared is listed again in the FRC section, because members who join in year 2 skip FTC and would otherwise never see it.

**Exercises 18–20 move real hardware and require a mentor present.** That's a safety rule, not a pacing one.

### FRC

21. [Intro to FRC Controls](https://docs.google.com/presentation/d/1U8EKEZv5Km__JKcN2SpE7tU8HjkMOnHZUupBr-Zo96M/edit?usp=sharing) — **Presentation** · borrowed, Spectrum 3847 (C1.2) · replace by 2027
22. [Intro to Vision Systems](https://docs.google.com/presentation/d/18Km6PWV-6Slt5ESQbFIYo8DxL3BhUzXH_tmMuM71YTA/edit?usp=sharing) — **Presentation** · same deck as item 13
23. [Install FRC Software Tools](https://docs.google.com/presentation/d/15QwOjFgt3fmCyq47i2P-bYuNClqwuyBc8TE3cleV4-c/edit?usp=sharing) — **Presentation** · borrowed, Spectrum 3847 (C2.0) · replace by 2027
24. Beginner FRC Programming — **Presentation** · _we don't have this yet_
25. Subsystems and Commands — **Presentation** · _we don't have this yet_
26. Intro to FRC Apps, Dashboards and Logging — **Presentation** · _we don't have this yet_
27. [Beginner Motors for FRC](https://docs.google.com/presentation/d/1mY7ZgkHr2y7-nbhTbuT59DtMnN5ITxR3q-kx6YO6MyI/edit?usp=sharing) — **Presentation** · borrowed, Spectrum 3847 (C2.3) · replace by 2027
28. Encoders — **Presentation** · _link needed_
29. Programming Best Practices — **Presentation** · same deck as item 16
30. Control Loops: PID and Motion Magic — **Presentation** · same deck as item 17
31. [Open Loop Motor Control](motor-control/01-open-loop.md) — **Exercise** · same as item 18 · mentor supervised
32. [Velocity Control with PID and Feedforward](motor-control/02-velocity-pid.md) — **Exercise** · same as item 19 · mentor supervised
33. [Position Control with PID](motor-control/03-position-pid.md) — **Exercise** · same as item 20 · mentor supervised
34. [Position with an External Encoder](motor-control/04-external-encoder.md) — **Exercise** · FRC only · mentor supervised
35. [Motion Magic](motor-control/05-motion-magic.md) — **Exercise** · FRC only · mentor supervised

Members who did FTC in year 1 have already seen items 22, 29, 30 and done exercises 31–33. Members who joined in year 2 meet all of them here.

**Items 1–10 are for members who join in year 2 without Java.** Existing FRC members skip them, which is why they aren't columns on the FRC progress sheet.

---

Some material is borrowed from other teams while we write our own. Borrowed items say so above, with the season we intend to replace them.

Control theory isn't a separate section — the FTC-level pass is item 17 and the FRC-level pass is item 30, which are the same deck. Members meet it once in year 1 and go over it again, deeper, in year 2.
