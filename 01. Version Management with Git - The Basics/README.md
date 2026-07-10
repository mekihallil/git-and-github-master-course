# Git & GitHub Complete Learning Guide

A beginner-friendly, hands-on reference for everything Git and GitHub.
Every command explained in simple language with real examples.

---

## About This Repository

This repository is my personal Git and GitHub learning journal.
It documents every command I learned, what it does, why it exists,
and when to use it — written in the simplest way possible.

If you are a beginner, this guide is for you too.

---

## My Learning Goals

- Understand how Git works from the ground up
- Use GitHub to store and share my projects
- Manage code changes confidently
- Collaborate with other developers professionally

---

## Complete Command Reference


## 🖥️ 1. Windows Command Line Basics

---

### `cd <folder>`
**What it does:** Move into a folder.
**Analogy:** Like double-clicking a folder to open it.
```cmd
cd projects
```

---

### `cd ..`
**What it does:** Go back one folder level.
**Analogy:** Like clicking the back button in File Explorer.
```cmd
cd ..
```

---

### `dir`
**What it does:** List all files and folders in current location.
**Analogy:** Like looking inside an open folder.
```cmd
dir
```

---

### `cls/clear`
**What it does:** Clear the terminal screen.
**When to use:** When the screen gets too cluttered.
```cmd
cls
```

---

### `echo Hello > file.txt`
**What it does:** Creates a new file and writes "Hello" inside it.
**Analogy:** Like creating a new text file and typing in it.
```cmd
echo Hello > file.txt
```

---

### `type/code file.txt`
**What it does:** Shows the content of a file in the terminal.
**Analogy:** Like opening a file to read it, without editing.
```cmd
type file.txt
```

---

### `del/rm file.txt`
**What it does:** Permanently deletes a file.
**Warning:** There is no undo. The file is gone.
```cmd
del file.txt
```

---

### `rmdir foldername`
**What it does:** Deletes an empty folder.
**To delete a folder with files inside:**
```cmd
rmdir /s /q foldername
```

---

### `copy source.txt destination.txt`
**What it does:** Copies a file to a new location.
**Analogy:** Like Ctrl+C and Ctrl+V for files.
```cmd
copy notes.txt backup_notes.txt
```

---

### `move file.txt folder\`
**What it does:** Moves a file into a folder.
**Analogy:** Like dragging a file into a folder.
```cmd
move notes.txt projects\
```

---

---

## 🔧 2. Git Configuration

> Tell Git who you are. Git stamps your name and email
> on every commit you make — like signing your work.

---

### `git config --global user.name "Your Name"`
**What it does:** Sets your name for all Git commits globally.
**Why it matters:** Every commit shows who made it.
```bash
git config --global user.name "Meki"
```

---

### `git config --global user.email "your@email.com"`
**What it does:** Sets your email for all Git commits globally.
**Why it matters:** GitHub uses this to link commits to your account.
```bash
git config --global user.email "Meki@email.com"
```

---

### Check your configuration
```bash
git config --list
```
**What it does:** Shows all your current Git settings.

---

## 📁 3. Repository Commands

> A repository (repo) is a folder Git is tracking.
> Think of it as a project folder with a memory.

---

### `git init`
**What it does:** Turns your current folder into a Git repository.
**When to use:** At the very start of a new project.
**Analogy:** Like giving your folder a memory to track all changes.
```bash
git init
```
**Output:**

---

### `git status`
**What it does:** Shows the current state of your files.
**Tells you:**
- Which files are changed
- Which files are staged
- Which files are untracked
```bash
git status
```
**Output:**

---

### `git add <file>`
**What it does:** Stages a specific file — prepares it for commit.
**Analogy:** Like putting items in a box before sealing it.
```bash
git add index.html
```

---

### `git add .`
**What it does:** Stages ALL changed files at once.
```bash
git add .
```

---

### `git log`
**What it does:** Shows the full history of all commits.
**Analogy:** Like reading a diary of every change ever made.
```bash
git log
```
**Cleaner version:**
```bash
git log --oneline
```
**Output:**

---


## 🌿 4. Branching

> A branch is an independent copy of your project
> where you can work safely without affecting the main code.
> Analogy: Like working on a photocopy of a document
> instead of the original.

---

### `git branch`
**What it does:** Lists all branches in your repository.
```bash
git branch
```
**Output:**


The `*` shows which branch you are currently on.

---

### `git branch <branch-name>`
**What it does:** Creates a new branch.
**When to use:** When starting a new feature or fix.
```bash
git branch feature/login
```

---

### `git switch <branch-name>`
**What it does:** Switches to an existing branch.
**Modern command** — use this instead of `git checkout`.
```bash
git switch feature/login
```

---

### `git switch -c <new-branch>`
**What it does:** Creates a new branch AND switches to it immediately.
**The `-c` stands for:** create
```bash
git switch -c feature/signup
```

---

### `git checkout <branch-name>` *(old way)*
**What it does:** Same as `git switch` but older syntax.
**Still works** but `git switch` is cleaner and recommended.
```bash
git checkout feature/login
```

---

## 🔀 5. Merging

> Merging combines changes from one branch into another.
> Analogy: Like copying your edits from the photocopy
> back into the original document.

---

### `git merge <branch-name>`
**What it does:** Merges the named branch into your current branch.
```bash
git switch main
git merge feature/login
```

---

### Fast-Forward Merge
Happens when main has no new commits since the branch was created.
Git simply moves the pointer forward — clean and simple.


---

### Three-Way Merge
Happens when both main and the branch have new commits.
Git creates a new merge commit combining both.


---

### Merge Conflict
Happens when both branches changed the same line.
Git cannot decide which version to keep — you must fix it manually.


**Fix:** Edit the file, remove the markers, then:
```bash
git add <file>
git commit -m "resolve merge conflict"
```

---

## 🔍 6. Tracking Files

> Git puts files into three categories:
> Tracked, Untracked, and Staged.

---

### `git ls-files`
**What it does:** Shows all files Git is currently tracking.
```bash
git ls-files
```
**Output:**

---

### `git rm <file-name>`
**What it does:** Removes a file from Git tracking AND deletes it.
**Warning:** This deletes the file from your computer too.
```bash
git rm old-file.txt
```

**To stop tracking without deleting the file:**
```bash
git rm --cached old-file.txt
```

---
## ↩️ 7. Undoing Unstaged Changes

> You edited a file but have NOT staged it yet
> and want to go back to the last saved version.

---

### `git restore <file-name>` ✅ Modern
**What it does:** Discards all changes in a file since last commit.
**Warning:** Changes are permanently lost.
```bash
git restore index.html
```

---

### `git restore -p <file-name>`
**What it does:** Lets you undo specific lines instead of the whole file.
**The `-p` stands for:** `--patch`
```bash
git restore -p index.html
```
**Interactive options:**
| Key | Action |
|-----|--------|
| `y` | Undo this chunk |
| `n` | Keep this chunk |
| `s` | Split into smaller pieces |
| `e` | Edit manually which lines to undo |
| `q` | Quit |

---

### `git checkout <file-name>` *(old way)*
**What it does:** Same as `git restore` but older syntax.
```bash
git checkout index.html
```

---

## 🧹 8. Deleting Untracked Files

> Untracked files are new files Git has never seen before.
> These commands permanently delete them.

---

### `git clean -dn`
**What it does:** PREVIEW — shows which files WOULD be deleted.
**Always run this first** before actually deleting.
```bash
git clean -dn
```
**Output:**


---

### `git clean -df`
**What it does:** Actually deletes all untracked files and folders.
**Warning:** Cannot be undone.
```bash
git clean -df
```

---

## 📤 9. Undoing Staged Changes

> You staged a file with `git add` but want to unstage it
> before committing.

---

### `git restore --staged <file-name>` ✅ Modern
**What it does:** Removes file from staging area.
**Your changes are kept** — just unstaged.
```bash
git restore --staged index.html
```

---

### `git reset <file-name>`
**What it does:** Same as above — unstages the file.
**Your changes are kept** in the working directory.
```bash
git reset index.html
```

---

## ⏪ 10. Removing Commits (Reset)

> HEAD~1 means "go back 1 commit".

---

### `git reset --soft HEAD~1`
**What it does:** Removes the last commit.
**Your changes:** Kept and still staged — ready to re-commit.
**Analogy:** Unsealing a box but keeping everything inside it.
```bash
git reset --soft HEAD~1
```

---

### `git reset HEAD~1` *(Mixed — default)*
**What it does:** Removes the last commit.
**Your changes:** Kept but unstaged — back in working directory.
**Analogy:** Unsealing the box AND unpacking the items.
```bash
git reset HEAD~1
```

---

### `git reset --hard HEAD~1`
**What it does:** Removes the last commit.
**Your changes:** Completely deleted — cannot be recovered.
**Analogy:** Throwing the sealed box in the trash.
```bash
git reset --hard HEAD~1
```
