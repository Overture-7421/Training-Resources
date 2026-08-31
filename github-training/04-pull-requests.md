# Exercise 4 — Pull Requests

**Category:** Collaboration
**Prerequisites:** [Exercise 3](03-branches.md). Do this one in pairs, in a shared repo.

**Concepts:** pushing a branch, opening a pull request, review, review comments, merging, keeping `main` working.

A pull request is a branch plus a conversation. That's it. The technical part they already know from Exercise 3; what's new is that somebody reads the change before it lands.

This is how the team works during build season, so run it on a shared practice repo with everyone in it — not on the robot code, and not on eight separate personal repos.

## Task

**Set up.** One shared repo, everyone on the team added as a collaborator. Seed it with a couple of the Java files from the Java track.

**Each student, individually:**

1. `git pull` on `main` first. Always start from current code.
2. `git switch -c your-name-feature`
3. Make a small, real change. One method, not a rewrite.
4. Commit, then `git push -u origin your-name-feature`
5. On github.com, open the pull request. Write a description that says *what changed and why*. Two sentences is fine; empty is not.

**Then swap.** Everyone reviews somebody else's PR:

- Read the Files changed tab.
- Leave at least one comment on a specific line. A question counts — "what happens if this is negative?" is a real review comment.
- Approve it, or request changes.

**Then close the loop.** The author responds, pushes another commit to the same branch, and the PR updates on its own. Nobody opens a second PR. When it's approved, merge it on GitHub and delete the branch.

**Finally, everyone runs `git pull` on `main`** and sees their teammates' work show up.

## Part B — The stale branch

After a few PRs have merged, have someone open a PR from a branch they made *before* those merges. GitHub will say it's out of date, or flag a conflict. The fix is the same as Exercise 3: pull `main` into their branch, resolve, push again.

This is the situation that actually eats build-season hours, so it's worth doing once on purpose in a calm room.

## Stretch

- Turn on branch protection for `main`, requiring one approval. Then try to push straight to `main` and read the rejection.
- Write a PR template (`.github/pull_request_template.md`) as a team.
- Link a PR to an issue with "Closes #3" and watch the issue close on merge.
- Look at the commit history of an actual FRC team's public robot repo and read a few real PRs.

## Watch for

- **Committing straight to `main`.** The habit to break. If it keeps happening, turn on branch protection and let the server enforce it.
- **Branching off a stale `main`.** Every PR should start with `git pull` on `main`. Say it until it's automatic.
- **PRs with 40 changed files.** Nobody reviews those honestly — they just click approve. Small PRs get real review. Enforce this early.
- **Rubber-stamp approvals.** If a review takes four seconds, it didn't happen. Require one specific comment per review, at least while they're learning.
- **Review tone.** "This is wrong" versus "what happens if the sensor reads zero here?" Teach them to comment on the code, not the person. This matters more than any Git command in the set.
- Opening a PR against the wrong base branch, or from the wrong branch. Have them read the "from → into" line at the top of the PR before clicking create.
- Forgetting the branch still exists locally after merging on GitHub. `git switch main`, `git pull`, `git branch -d <branch>`.

---

[← Exercise 3](03-branches.md) · [Index](README.md)
