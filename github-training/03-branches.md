# Exercise 3 — Branches

**Category:** Collaboration
**Prerequisites:** [Exercise 2](02-push-and-pull.md)

**Concepts:** `git branch`, `git switch`, `git merge`, merge conflicts, deleting branches.

Up to now there's been one line of history. Branches let two people work on the same code at once without overwriting each other, which is the entire reason the team uses Git during build season.

The moment that sells this exercise is switching branches and watching a file change on disk. Don't rush past it.

## Part A — Make a branch

```
git switch -c intake-subsystem
```

Change a file. Commit. Then:

```
git switch main
```

Open the file. Their change is gone. Let them sit in that for a second before explaining — nothing was lost, they're just looking at a different version of history. `git switch intake-subsystem` brings it back.

Run `git branch` and `git log --oneline --graph --all` to see the shape.

## Part B — Merge

Back on `main`:

```
git merge intake-subsystem
git branch -d intake-subsystem
```

The change is now on `main`, and the branch is gone because it served its purpose.

## Part C — Cause a conflict on purpose

This is the part students actually need.

1. From `main`, make two branches: `driver-a` and `driver-b`.
2. On each one, change **the same line** of the same file to something different. Commit both.
3. Merge `driver-a` into `main`. It works.
4. Merge `driver-b` into `main`. It doesn't.

Open the file and read the conflict markers together:

```
<<<<<<< HEAD
motor.setPower(0.5);
=======
motor.setPower(0.8);
>>>>>>> driver-b
```

Explain it plainly: Git is not confused and nothing is broken. Two people changed the same line and Git will not guess which one is right. A human decides.

Resolve it by editing the file into what it should be — **deleting all three marker lines** — then `git add` the file and `git commit`.

## Stretch

- `git switch -` to jump back to the previous branch.
- Make a branch, commit twice, then `git log --oneline --graph --all` and have them draw the shape on a whiteboard.
- `git merge --abort` in the middle of a conflict, to show it's always safe to back out and start over.
- Branch naming conventions. Agree on one as a team now — `intake-pid`, not `test2`.

## Watch for

- **Conflict markers committed into the file.** The code won't compile and `<<<<<<<` is sitting in the middle of it. Happens constantly. Teach them to search for `<<<<` before every commit after a conflict.
- **Resolving by deleting the other person's work.** Technically resolves the conflict, quietly loses a teammate's change. Ask out loud each time: do we want mine, theirs, or a combination?
- **"I lost my code."** Almost always they're on a different branch than they think. `git status` and `git branch` answer it. Say it as often as you have to: their work is not gone, they're looking at a different branch.
- **Uncommitted changes blocking a switch.** Git refuses to switch and prints a clear message. Commit first. Don't teach `git stash` yet — it's one more thing to lose track of.
- Working on `main` by accident for an hour before remembering to branch.
- Panic. Conflicts feel like breakage to beginners. Stay calm about it and they will too.

---

[← Exercise 2](02-push-and-pull.md) · [Index](README.md) · [Exercise 4 →](04-pull-requests.md)
