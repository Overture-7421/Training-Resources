# Exercise 2 — Push and Pull

**Category:** Git basics
**Prerequisites:** [Exercise 1](01-commits.md). A GitHub account, and an invite to the team organization.

**Concepts:** remotes, `origin`, `git remote add`, `git push`, `git pull`, `git clone`, authentication.

Now GitHub enters. The mental model to land: GitHub is a copy of the repo that lives on a server. It is not magic and it is not automatic. Nothing leaves their laptop until they push, and nothing arrives until they pull.

## Task

**Part A — Get the local repo onto GitHub.**

1. Create an empty repo on github.com. No README, no `.gitignore`, no license — those create commits and make the first push messier than it needs to be.
2. Follow the "push an existing repository" commands GitHub shows:

```
git remote add origin <url>
git branch -M main
git push -u origin main
```

3. Refresh the GitHub page. Their code is there. Let that land.

**Part B — Prove nothing is automatic.**

Change a file locally and commit it. Refresh GitHub. It hasn't changed. Ask them why, then push and refresh again.

**Part C — Pull.**

Edit a file directly on github.com using the web editor and commit it there. Now the server has a commit their laptop doesn't. Run `git status` — Git has no idea. Then `git pull` and watch it arrive.

**Part D — Clone.**

Have them delete their local folder entirely, then `git clone <url>`. Everything comes back, full history included. This is also how they'll get the team's robot code on the first day of build season.

## Stretch

- `git remote -v`. Ask what `origin` actually is — it's just a nickname for a URL.
- Two students clone the same repo, both push, and see what the second one hits.
- `git log --oneline --all` after a pull, to see the commits from GitHub sitting alongside their own.
- Set up SSH keys instead of HTTPS.

## Watch for

- **Authentication is the whole difficulty of this exercise.** GitHub stopped accepting account passwords over HTTPS years ago, so "password authentication is not supported" confuses everyone. Sort this out *before* the session, not during it. Easiest path is `gh auth login` with the GitHub CLI. Otherwise a personal access token used as the password, or SSH keys.
- **`main` vs. `master`.** Older Git installs still default to `master` while GitHub expects `main`. That's what `git branch -M main` is for. If a student's push creates a second branch, this is why.
- **`! [rejected] ... fetch first`.** The server has commits they don't. This is the single most common push error and the fix is always `git pull` first. They'll hit it constantly in Exercise 4, so make sure they recognize it here.
- **Pushing to a repo initialized with a README.** The histories are unrelated and the error is genuinely confusing for a beginner. Avoid it by creating the repo empty.
- Students who think pushing is a save button and commit once a day with everything in it.
- Cloning inside an existing repo folder, ending up with a repo inside a repo.

---

[← Exercise 1](01-commits.md) · [Index](README.md) · [Exercise 3 →](03-branches.md)
