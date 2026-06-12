# 🌳 20-Git-Advanced.md

# Git Advanced

## Rebase, Cherry-Pick, Reset, Revert, Reflog, Stash, Tags & Git Internals

> Most developers know:
>
> ```bash
> git add
> git commit
> git push
> ```
>
> But advanced Git is what separates beginners from professional engineers.
>
> Understanding Git internals helps you recover mistakes, manage complex workflows, and collaborate effectively in large teams.

---

# 📚 Table of Contents

1. Why Learn Advanced Git?
2. Git Architecture Refresher
3. Git Internals
4. HEAD
5. Branching Strategy
6. Merge
7. Rebase
8. Merge vs Rebase
9. Cherry Pick
10. Stash
11. Reset
12. Revert
13. Reflog
14. Tags
15. Git Hooks
16. Git Workflow in Industry
17. Recovering Mistakes
18. Common Commands
19. Interview Questions

---

# Chapter 1: Why Learn Advanced Git?

Most daily work involves:

```text
Branches
Pull Requests
Code Reviews
Bug Fixes
Release Management
```

---

Advanced Git helps:

```text
Clean Commit History
Recover Deleted Work
Manage Releases
Handle Merge Conflicts
```

---

# Chapter 2: Git Architecture Refresher

Git consists of:

```text
Working Directory
       ↓
Staging Area
       ↓
Repository
```

---

Flow:

```text
File
 ↓
git add
 ↓
Staging Area
 ↓
git commit
 ↓
Repository
```

---

# Chapter 3: Git Internals

Git is:

```text
Distributed Version Control System
```

---

Git stores:

```text
Commits
Trees
Blobs
References
```

---

Think:

```text
Git
  =
Database Of Snapshots
```

---

Each commit:

```text
Points To Previous Commit
```

creating a chain.

---

Architecture:

```text
Commit C
   ↓
Commit B
   ↓
Commit A
```

---

# Chapter 4: HEAD

HEAD is:

```text
Current Position
In Git History
```

---

Example:

```text
main
  ↓
HEAD
```

---

View:

```bash
git log
```

---

Think:

```text
HEAD
   =
Bookmark
```

for your current commit.

---

# Chapter 5: Branching Strategy

Branches allow independent work.

---

Example:

```text
main

feature-login

feature-payment

bugfix-auth
```

---

Architecture:

```text
main
  │
  ├── feature-login
  │
  └── feature-payment
```

---

Benefits:

```text
Isolation
Parallel Development
Safe Experimentation
```

---

# Chapter 6: Merge

Merge combines branches.

---

Example:

```text
feature-login
      ↓
      Merge
      ↓
main
```

---

Command:

```bash
git merge feature-login
```

---

Result:

```text
main
  │
  ├── Merge Commit
```

---

# Chapter 7: Rebase

Rebase rewrites history.

---

Instead of:

```text
main
  │
  ├── commit1
  │
feature
  ├── commit2
```

---

Rebase:

```text
main
  │
  ├── commit1
  ├── commit2
```

---

Command:

```bash
git rebase main
```

---

Purpose:

```text
Linear Commit History
```

---

# Chapter 8: Merge vs Rebase

Most Asked Interview Question.

---

## Merge

Preserves history.

Creates merge commit.

---

Example:

```text
A
 \
  B
   \
    Merge
```

---

## Rebase

Rewrites history.

Cleaner timeline.

---

Example:

```text
A
 ↓
B
 ↓
C
```

---

Comparison:

| Merge                  | Rebase           |
| ---------------------- | ---------------- |
| Safe                   | Rewrites History |
| Keeps Branch Structure | Cleaner History  |
| Creates Merge Commit   | No Merge Commit  |

---

Easy Memory:

```text
Merge
   =
Combine Histories

Rebase
   =
Rewrite History
```

---

# Chapter 9: Cherry Pick

Cherry-pick copies a specific commit.

---

Example:

```text
feature branch
   ↓
commit X
```

---

Copy:

```bash
git cherry-pick <commit-id>
```

---

To:

```text
main branch
```

---

Use Case:

```text
Move Specific Fix
Without Merging Entire Branch
```

---

# Chapter 10: Stash

Temporary storage.

---

Imagine:

```text
Work In Progress
```

but need to switch branches.

---

Store Changes:

```bash
git stash
```

---

Restore:

```bash
git stash pop
```

---

Flow:

```text
Changes
   ↓
Stash
   ↓
Switch Branch
   ↓
Restore
```

---

# Chapter 11: Reset

Reset moves HEAD backward.

---

Soft Reset:

```bash
git reset --soft HEAD~1
```

---

Keeps changes.

---

Hard Reset:

```bash
git reset --hard HEAD~1
```

---

Deletes changes.

---

Interview Warning:

```text
Hard Reset
Can Lose Data
```

---

# Chapter 12: Revert

Revert safely undoes a commit.

---

Command:

```bash
git revert <commit-id>
```

---

Creates:

```text
New Commit
```

that reverses changes.

---

Safe for shared branches.

---

# Chapter 13: Reflog

Most powerful recovery command.

---

Shows:

```text
Everything HEAD Has Visited
```

---

Command:

```bash
git reflog
```

---

Example:

```text
commit A
commit B
commit C
```

Even deleted commits can be recovered.

---

Recovery:

```bash
git reset --hard <reflog-id>
```

---

Interview Favorite:

```text
Reflog
Can Recover Lost Commits
```

---

# Chapter 14: Tags

Tags mark releases.

---

Example:

```text
v1.0
v1.1
v2.0
```

---

Create:

```bash
git tag v1.0
```

---

Push:

```bash
git push origin v1.0
```

---

Use Case:

```text
Release Management
```

---

# Chapter 15: Git Hooks

Hooks automate actions.

---

Examples:

```text
Pre-Commit
Post-Commit
Pre-Push
```

---

Use Cases:

```text
Code Formatting
Security Checks
Linting
Testing
```

---

# Chapter 16: Git Workflow In Industry

Typical Workflow:

```text
Developer
   ↓
Feature Branch
   ↓
Commit
   ↓
Push
   ↓
Pull Request
   ↓
Code Review
   ↓
Merge
   ↓
Deployment
```

---

Architecture:

```text
main
  │
  ├── feature-auth
  ├── feature-api
  └── bugfix-login
```

---

# Chapter 17: Recovering Mistakes

Deleted Commit?

```bash
git reflog
```

---

Wrong Commit Message?

```bash
git commit --amend
```

---

Wrong Branch?

```bash
git cherry-pick
```

---

Temporary Work?

```bash
git stash
```

---

# Chapter 18: Common Commands

Create Branch:

```bash
git checkout -b feature-login
```

---

Switch Branch:

```bash
git checkout main
```

---

Rebase:

```bash
git rebase main
```

---

Cherry Pick:

```bash
git cherry-pick <commit-id>
```

---

Stash:

```bash
git stash
```

---

Reflog:

```bash
git reflog
```

---

Tag:

```bash
git tag v1.0
```

---

Reset:

```bash
git reset --soft HEAD~1
```

---

Revert:

```bash
git revert <commit-id>
```

---

# Chapter 19: Why Git Matters In DevOps

Everything starts with Git.

---

Flow:

```text
Developer
   ↓
Git
   ↓
GitHub
   ↓
Webhook
   ↓
CI/CD
   ↓
Deployment
```

---

Without Git:

```text
No CI/CD
No Collaboration
No Version Control
```

---

# 🔥 Interview Questions

### What Is HEAD?

HEAD points to the currently checked-out commit.

---

### What Is Rebase?

Rebase moves commits onto another base commit and creates a linear history.

---

### Merge vs Rebase?

Merge combines histories.

Rebase rewrites history.

---

### What Is Cherry Pick?

Copies a specific commit from one branch to another.

---

### What Is Stash?

Temporarily stores uncommitted changes.

---

### What Is Reset?

Moves HEAD backward and optionally removes commits.

---

### What Is Revert?

Creates a new commit that undoes a previous commit.

---

### What Is Reflog?

Tracks all HEAD movements and helps recover lost commits.

---

### What Are Tags?

Named references used to mark releases.

---

### Why Is Git Distributed?

Each developer has a complete copy of the repository and its history.

---

# Mental Model

```text
Working Directory
      ↓
git add
      ↓
Staging Area
      ↓
git commit
      ↓
Repository
      ↓
git push
      ↓
GitHub
      ↓
CI/CD
```

---

# Git Recovery Toolkit

```text
Lost Commit?
    → reflog

Wrong Commit?
    → amend

Undo Commit?
    → revert

Move Commit?
    → cherry-pick

Temporary Work?
    → stash

Clean History?
    → rebase
```

---

# One-Line Summary

Advanced Git provides powerful tools such as rebase, cherry-pick, stash, reset, revert, reflog, and tags that enable engineers to manage code history, recover mistakes, and maintain clean collaboration workflows in modern software development.
