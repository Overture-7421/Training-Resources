# Exercise 1 — Your First Commits

**Category:** Git basics
**Prerequisites:** none. A terminal and Git installed.

**Concepts:** `git init`, the three areas (working directory, staging, history), `git status`, `git add`, `git commit`, `git log`, `.gitignore`.

Everything in this exercise happens on one machine. No GitHub account yet, no internet. Git and GitHub are two different things and students should feel that separation before the two get blurred together.

Use the Java files they wrote in the Java track as the material. Committing code they actually recognize beats committing `test.txt`.

## Task

**Set up once.** Git refuses to commit until it knows who you are:

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**Then, in a folder with their Java exercises:**

1. `git init`
2. `git status` — read the output together. Everything is untracked.
3. `git add RobotStats.java`
4. `git status` again. The file moved. Ask them to say where it went.
5. `git commit -m "Add robot stats card"`
6. `git log`

Then change the file, and run `status`, `add`, `commit`, `log` again. Do it three or four times until the cycle is boring. Boring is the goal.

**Then a `.gitignore`.** Compile the Java. `git status` now lists `.class` files. Ask whether those belong in history — the answer is no, they're rebuilt from source every time. Add a `.gitignore` with `*.class`, run `status` again, watch them disappear.

## Stretch

- `git log --oneline` and `git log -p`. The second one shows exactly what changed in each commit.
- `git diff` before adding, and `git diff --staged` after. The difference between those two is the clearest picture of what staging actually is.
- `git show <hash>` on an old commit.
- Have them write commit messages for each other's changes without seeing the code, using only `git diff`. Bad messages get exposed fast.

## Watch for

- **No identity configured.** The very first commit fails with a wall of text about `user.email`. Let it happen and read it together — it's a friendly error and a good first lesson in reading Git output.
- **`git commit` with no `-m`.** This drops them into Vim and they cannot get out. Teach `-m` from the start. If someone lands there anyway: `Esc`, then `:q!`, then Enter.
- **Committing without adding**, then wondering why the commit is empty or missing their change. Send them back to `git status` every time. `status` is the answer to almost every question in this exercise.
- **Commit messages like "stuff", "fix", "asdf".** Correct this on day one or it never gets corrected. The message should finish the sentence "this commit will…".
- Committing `.class` files, or the whole `bin/` folder, before the `.gitignore` step. Let it happen. Removing something already committed is harder than ignoring it up front, which is the point.
- Running Git commands outside the repo folder. `fatal: not a git repository` means they're in the wrong directory.

---

[Index](README.md) · [Exercise 2 →](02-push-and-pull.md)
