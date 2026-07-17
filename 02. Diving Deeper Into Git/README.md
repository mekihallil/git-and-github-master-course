## 📦 15. Understanding the Stash (git stash)

> `git stash` temporarily saves your uncommitted changes
> so you can switch tasks without committing half-finished work.
> Analogy: Like sweeping your messy desk into a drawer
> so you can quickly work on something else — you can
> take it back out whenever you want.

---

### Why You Need `git stash`
**What it does:** Saves your uncommitted (tracked) changes and gives you a clean working directory.
**Why it is used:** So you can switch branches or handle something urgent without losing your work-in-progress.
**When to use:** When your changes are not ready to commit, but you need a clean state right now.

---

### `git stash`
**What it does:** Saves your current uncommitted changes and reverts your working directory to the last commit.
```bash
git stash
```
**Output:**



## 🕰️ 16. Bringing Lost Data Back with git reflog

> `git reflog` records every single move your HEAD has made —
> commits, resets, checkouts, merges — even ones you "lost."
> Analogy: Like a security camera recording every move you make
> in your repository, even the mistakes.

---

### `git reflog`
**What it does:** Shows a log of everywhere your HEAD has pointed to, including deleted commits.
**Why it is used:** To recover commits that seem lost — for example, after a `git reset --hard`.
**When to use:** Anytime you think you've lost work and need to find it again.
```bash
git reflog
```
**Output:**


## 🔀 17. Combining Branches — What & Why?

> Combining branches means bringing the work from one branch
> into another so the code lives together in one place.
> Analogy: Like combining edits from two people's photocopies
> back into a single, final document.

**Why it is used:** Multiple people (or you) work on separate branches to avoid breaking the main code. Eventually, that work needs to come together — this is what merging is for.

**When to use:** After a feature, fix, or experiment is finished and tested, and it's ready to join the main codebase.

---

## 🧬 18. Understanding Merge Types

> Git decides HOW to merge automatically, based on your
> branch history. There are two main types you'll see:
> **Fast-Forward** and **Recursive (Three-Way)**.

| Merge Type | Happens when | Creates a merge commit? |
|---|---|---|
| Fast-Forward | Main has no new commits since branching | ❌ No — just moves the pointer |
| Recursive (Three-Way) | Both branches have new commits | ✅ Yes — combines both histories |


## ⏩ 19. Applying the Fast-Forward Merge

> Fast-forward merge happens when the branch you're merging
> IN has all the commits main is missing, and main hasn't moved.
> Analogy: Like main was "asleep" while your branch worked —
> Git just moves main's bookmark forward to catch up.

**What it does:** Moves the current branch pointer forward to match the merged branch — no new commit is created.
**Why it is used:** It keeps history clean and linear when there's no divergence to resolve.
**When to use:** When `main` hasn't changed since you created your feature branch.

```bash
git switch main
git merge feature/login
```
**Output:**


## 🔗 20. The Recursive Merge (Non-Fast-Forward)

> Recursive merge happens when BOTH branches have new commits
> since they diverged. Git combines both histories into
> a brand-new merge commit.
> Analogy: Like two people editing the same document
> separately — Git creates a new page that combines
> both sets of edits.

**What it does:** Creates a new merge commit that has two parent commits — one from each branch.
**Why it is used:** To preserve the full history of both branches instead of rewriting it.
**When to use:** When main has moved forward since you branched off (the normal case in team projects).

```bash
git switch main
git merge feature/signup
```
**Output:**


## 🪄 21. Rebasing — Theory

> Rebasing takes the commits from your branch and replays them
> on top of another branch — as if you had started your work
> from the latest point, not the old one.
> Analogy: Like taking your handwritten notes and rewriting them
> neatly at the end of someone else's notebook, instead of
> stapling a separate messy page (merge) into it.

---

### Why Rebase Instead of Merge?
**What it does:** Moves (replays) your branch's commits onto the tip of another branch, creating a clean, linear history.
**Why it is used:** Avoids extra "merge commits" cluttering your history — makes `git log` easier to read.
**When to use:** When you want a clean, straight-line history, usually before merging a feature branch into main, or to update your branch with the latest main changes.

---

### Merge vs Rebase — Quick Comparison

| | Merge | Rebase |
|---|---|---|
| History shape | Branching, non-linear | Straight line |
| Creates a merge commit? | ✅ Yes (if not fast-forward) | ❌ No |
| Original commits changed? | ❌ No | ✅ Yes — new commit hashes |
| Safe on shared/public branches? | ✅ Yes | ⚠️ Risky — avoid on shared branches |
| Best for | Preserving exact history | Clean, readable history |

---

### ⚠️ The Golden Rule of Rebasing
> **Never rebase a branch that others are already using/pulling from.**
> Rebasing rewrites commit history (new commit hashes), so if someone
> else has the old commits, you'll create conflicts and confusion
> for their copy of the branch.
> Analogy: Like secretly rewriting pages in a shared notebook —
> anyone else with a copy of the old pages is now out of sync.

| Situation | Safe to rebase? |
|---|---|
| Local branch, not pushed yet | ✅ Yes |
| Your own feature branch, not shared | ✅ Yes |
| Branch already pushed and others are using it | ❌ No — use merge instead |
| Updating your branch with latest main changes | ✅ Yes (before pushing/sharing) |

---

## 🔧 22. Applying "git rebase"

---

### `git rebase <branch-name>`
**What it does:** Replays your current branch's commits on top of the specified branch's latest commit.
**Why it is used:** To keep your feature branch up to date with `main` without creating a merge commit.
**When to use:** Before merging your feature branch, to make sure it's based on the latest code and history stays clean.

```bash
git switch feature/login
git rebase main
```
**Output (success):**