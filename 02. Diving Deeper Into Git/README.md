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