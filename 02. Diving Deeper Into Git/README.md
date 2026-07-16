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