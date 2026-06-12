# 🌳 Git Cheat Sheet

> Quick Revision Guide for Git, GitHub, CI/CD, DevOps & Interviews

---

# 🎯 What is Git?

Git is a **Distributed Version Control System (DVCS)** used to track source code changes and collaborate with teams.

---

# 🗺 Git Workflow

```text
Working Directory
        ↓
git add
        ↓
Staging Area
        ↓
git commit
        ↓
Local Repository
        ↓
git push
        ↓
Remote Repository (GitHub)
```

---

# ⚙️ Initial Setup

## Configure Username

```bash
git config --global user.name "Dhondi Saiteja"
```

---

## Configure Email

```bash
git config --global user.email "example@gmail.com"
```

---

## Verify Configuration

```bash
git config --list
```

---

# 📥 Clone Repository

## Clone Existing Repository

```bash
git clone https://github.com/user/repo.git
```

---

## Clone Specific Branch

```bash
git clone -b dev https://github.com/user/repo.git
```

---

# 📂 Repository Status

## Check Status

```bash
git status
```

Shows:

```text
Modified Files
New Files
Deleted Files
Staged Files
```

---

# ➕ Staging Changes

## Add Single File

```bash
git add file.txt
```

---

## Add Multiple Files

```bash
git add file1 file2
```

---

## Add Everything

```bash
git add .
```

---

# 💾 Commit Changes

## Commit

```bash
git commit -m "Added login feature"
```

---

## Commit Staged Changes Quickly

```bash
git commit -am "Fixed bug"
```

---

# 📤 Push Changes

## Push To Remote

```bash
git push origin main
```

---

## Push New Branch

```bash
git push -u origin feature-login
```

---

# 📥 Pull Changes

## Fetch + Merge

```bash
git pull origin main
```

---

## Fetch Only

```bash
git fetch
```

---

# 🌿 Branch Management

## View Branches

```bash
git branch
```

---

## Create Branch

```bash
git branch feature-login
```

---

## Switch Branch

```bash
git checkout feature-login
```

---

## Create And Switch

```bash
git checkout -b feature-login
```

Modern Git:

```bash
git switch -c feature-login
```

---

## Delete Branch

```bash
git branch -d feature-login
```

Force Delete:

```bash
git branch -D feature-login
```

---

# 🔀 Merge

## Merge Branch

```bash
git checkout main

git merge feature-login
```

---

## Merge Flow

```text
main
 │
 └── feature-login
         ↓
       Merge
         ↓
        main
```

---

# 🔥 Rebase

## Rebase Branch

```bash
git checkout feature-login

git rebase main
```

---

## Why Rebase?

Creates cleaner history.

Before:

```text
main
 ├─ commit
 ├─ commit
 └─ merge commit
```

After:

```text
main
 ├─ commit
 ├─ commit
 ├─ commit
 └─ commit
```

---

# 🎯 Merge vs Rebase

| Merge                | Rebase           |
| -------------------- | ---------------- |
| Preserves History    | Rewrites History |
| Creates Merge Commit | Cleaner History  |
| Safer                | More Powerful    |

---

# 📌 Git Log

## Commit History

```bash
git log
```

---

## One-Line History

```bash
git log --oneline
```

---

## Graph View

```bash
git log --graph --oneline --all
```

---

# ⏪ Undo Changes

## Unstage File

```bash
git restore --staged file.txt
```

---

## Discard Changes

```bash
git restore file.txt
```

---

## Reset Last Commit

```bash
git reset HEAD~1
```

---

# 🚨 Reset Types

## Soft Reset

```bash
git reset --soft HEAD~1
```

Keeps changes staged.

---

## Mixed Reset

```bash
git reset HEAD~1
```

Keeps changes in working directory.

---

## Hard Reset

```bash
git reset --hard HEAD~1
```

Deletes changes permanently.

---

# 📌 Git Revert

## Revert Commit

```bash
git revert COMMIT_ID
```

Creates a new commit that undoes previous changes.

Safe for shared repositories.

---

# 📦 Git Stash

## Save Work Temporarily

```bash
git stash
```

---

## View Stash

```bash
git stash list
```

---

## Restore Stash

```bash
git stash pop
```

---

## Delete Stash

```bash
git stash drop
```

---

# 🍒 Cherry Pick

## Copy Specific Commit

```bash
git cherry-pick COMMIT_ID
```

Example:

```text
Branch A
      ↓
Specific Commit
      ↓
Branch B
```

---

# 🏷 Tags

## Create Tag

```bash
git tag v1.0
```

---

## Push Tags

```bash
git push origin --tags
```

---

## View Tags

```bash
git tag
```

---

# 🔎 Git Diff

## Compare Changes

```bash
git diff
```

---

## Compare Staged Changes

```bash
git diff --cached
```

---

# 🌍 Remote Repositories

## View Remotes

```bash
git remote -v
```

---

## Add Remote

```bash
git remote add origin URL
```

---

## Change Remote URL

```bash
git remote set-url origin URL
```

---

# 🔐 Git + SSH

## Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096
```

---

## Start SSH Agent

```bash
eval "$(ssh-agent -s)"
```

---

## Add Key

```bash
ssh-add ~/.ssh/id_rsa
```

---

## Test GitHub Connection

```bash
ssh -T git@github.com
```

---

# 🚀 GitHub Workflow

```text
Developer
      ↓
git add
      ↓
git commit
      ↓
git push
      ↓
GitHub
      ↓
Pull Request
      ↓
Code Review
      ↓
Merge
```

---

# 📋 Pull Requests (PR)

Purpose:

```text
Code Review

Discussion

Approval

Merge
```

---

# 🔥 Most Used Commands

```bash
git status

git add .

git commit -m "message"

git push

git pull

git clone

git branch

git checkout

git merge

git rebase

git stash

git log
```

---

# 🎯 Interview Questions

## What is Git?

Distributed Version Control System.

---

## Git vs GitHub?

Git:

```text
Version Control Tool
```

GitHub:

```text
Cloud Platform Hosting Git Repositories
```

---

## What is Branching?

Creating isolated development environments.

---

## What is Merge?

Combining branches.

---

## What is Rebase?

Moving commits onto another base commit.

---

## What is Stash?

Temporary storage for uncommitted work.

---

## What is Cherry-Pick?

Copying a specific commit.

---

## What is a Pull Request?

Request to merge code into another branch.

---

# 🚨 Common Troubleshooting

## Undo Last Commit

```bash
git reset HEAD~1
```

---

## Recover Deleted Branch

```bash
git reflog
```

Find commit:

```bash
git checkout COMMIT_ID
```

---

## Resolve Merge Conflict

```bash
git status
```

Edit files manually.

Then:

```bash
git add .

git commit
```

---

# 🧠 Git Mental Model

```text
Working Directory
        ↓
Staging Area
        ↓
Commit
        ↓
Branch
        ↓
Push
        ↓
GitHub
```

---

# 🚀 Git Master Formula

```text
Code
 ↓
Add
 ↓
Commit
 ↓
Push
 ↓
Pull Request
 ↓
Review
 ↓
Merge
 ↓
Deploy
```

---

# 🎯 One-Line Revision

```text
Clone → Branch → Add → Commit → Push → Pull Request → Review → Merge
```
