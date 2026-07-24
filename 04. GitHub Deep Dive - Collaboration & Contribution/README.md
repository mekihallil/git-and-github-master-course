## 👤 42. Understanding GitHub Account Types

> GitHub offers different account types depending on whether
> you're an individual, a team, or a large company.
> Analogy: Like choosing between a personal bank account,
> a joint account, or a business account — same bank,
> different features and permissions.

---

### GitHub Account Types — Overview



## 🔒 43. Changing the Repository Type from Public to Private

> Repository visibility controls WHO can see your code.
> **Public** = anyone on the internet can view it.
> **Private** = only you and people you explicitly invite can view it.
> Analogy: Like switching a social media post from
> "Public" to "Only Me" — same content, different audience.

---

### Steps to Change Visibility

## 📢 44. Pushing Commits to a Public Repository

> Public repositories are visible to EVERYONE, including your
> full commit history, file contents, and commit messages —
> so extra caution is needed before pushing.
> Analogy: Like publishing a diary online — once it's posted,
> assume anyone in the world can read every page, including old ones.

---

## 🛡️ 45. How GitHub Manages Account Security

> GitHub protects your account and code using several layers
> of security — from login protection to code scanning.
> Analogy: Like a bank using a password, a physical key card,
> AND security cameras — multiple layers, not just one lock.

---

## 🤝 46. Understanding & Adding a Collaborator to a Private User Account

> A collaborator is someone you personally invite to work on
> YOUR repository — useful when you don't need a full
> organization, just an extra pair of hands.
> Analogy: Like giving a trusted friend a spare key to your
> apartment — they can come in and help, but it's still your place.

---

### Why Add a Collaborator
**What it does:** Grants another GitHub user push/pull access to your private (or public) repository.
**Why it is used:** So more than one person can contribute code, without making the repo public.
**When to use:** Working with a friend, freelancer, or teammate on a personal project/repo.

---

### Steps to Add a Collaborator

1) Go to your repository on GitHub
2) Click "Settings"
3) Click "Collaborators" in the left sidebar
4) Click "Add people"
5) Search their GitHub username or email
6) Click "Add <username> to this repository"
7) GitHub sends them an invitation email


## 👥 47. Collaborating in Private Repositories

> Once someone accepts a collaborator invite, they can work
> on the private repository almost like it's their own —
> cloning, branching, pushing, and opening pull requests.
> Analogy: Like being handed a key AND shown around the house —
> now you can move freely inside, following the house rules.

---

### Typical Collaboration Workflow
```bash
# Collaborator clones the private repo (needs access first)
git clone https://github.com/mekihallil/git-and-github-master-course.git
cd private-project

# Creates their own branch to avoid touching main directly
git switch -c feature/new-button

# Makes changes, commits
git add .
git commit -m "feat: add new call-to-action button"

# Pushes their branch
git push -u origin feature/new-button
```
**Output:**

> Even with collaborator access, it's best practice to work
> on **branches**, not directly on `main` — then use a Pull
> Request so the owner (or team) can review changes before
> they're merged.


## ⚖️ 48. Comparing Owner & Collaborator Rights

> Not everyone with access has the SAME power. The repository
> **Owner** always has full control; a **Collaborator** has
> limited permissions, decided by the owner.
> Analogy: Like a house owner vs. a guest with a key —
> the guest can use the house, but can't sell it or change the locks.

---
