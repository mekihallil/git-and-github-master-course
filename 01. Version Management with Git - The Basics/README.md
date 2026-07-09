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