# Git and GitHub

Track 2 of 5. See the [curriculum index](../README.md) for how this fits with the rest.

Four exercises covering the Git the team actually uses during build season: commits, push and pull, branches, and pull requests. Nothing more. Rebasing, cherry-picking, and rewriting history are deliberately not here — they aren't needed to work on a robot repo, and they're an excellent way to lose a beginner's work.

## Exercises

| # | Exercise | Category |
|---|----------|----------|
| 1 | [Your First Commits](01-commits.md) | Git basics |
| 2 | [Push and Pull](02-push-and-pull.md) | Git basics |
| 3 | [Branches](03-branches.md) | Collaboration |
| 4 | [Pull Requests](04-pull-requests.md) | Collaboration |

**Order matters.** Each exercise assumes the one before it.

**A mentor sets the pace.** Don't start an exercise before your mentor says to. See [How this is run](../README.md#how-this-is-run).

## What students need

- Git installed, and a terminal they can find.
- A GitHub account, added to the team organization.
- Working authentication. **Sort this out before the session.** See the Watch for section in Exercise 2 — auth is the one thing that reliably burns a whole meeting.
- The Java files they wrote in the [Java track](../java-training/README.md). The exercises use those as material so students are versioning code they recognize.

## Command line, not buttons

The exercises use the command line. VS Code, IntelliJ, and GitHub Desktop all have Git built in and students are welcome to use them afterward, but the buttons hide the model — especially the difference between staging, committing, and pushing. Learn it once where every step is visible, then use whatever is fastest.

## Notes for whoever is teaching

**Practice repos, not the robot repo.** Exercises 1–3 are on a throwaway repo. Exercise 4 needs a shared one, still not the robot code. Nobody's first merge conflict should be in a competition codebase.

**`git status` is the answer.** Most beginner confusion in this track is fixed by reading `status` output. Make it reflexive before anything else.

**Nothing here is unrecoverable.** Say this out loud and often. Beginners freeze on conflicts and detached-looking states because they think they've destroyed something. Committed work is essentially impossible to lose, and knowing that is the difference between a student who experiments and one who won't touch anything.

**Don't let students run ahead.** This track especially. Someone who reads Exercise 3 early and starts making branches in a shared repo unsupervised creates a mess for everyone else to untangle. Exercise 4 only works if the whole group arrives at it together.

**Pairing works well for Exercise 4** and badly for Exercise 1. Everyone needs their own hands on the first one.

## Next

The FTC or FRC track, depending on the year. Both assume students can clone a repo, work on a branch, and open a PR without help.

[← Curriculum index](../README.md)
