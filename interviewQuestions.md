# Git & GitHub Interview Q/A

## 📌 Section 1: Basics

### Q1. What is Git?

**Answer:** Git is a distributed version control system (DVCS) that helps track code changes, collaborate with teams, roll back to older versions, and manage branching/merging.
**💡 Pro Tip:** Always mention "distributed" — it highlights Git’s offline capability.

### Q2. What is GitHub?

**Answer:** GitHub is a cloud platform to host Git repositories and collaborate using Pull Requests, Issues, Actions (CI/CD), and project boards.
**💡 Pro Tip:** Git = tool, GitHub = platform.

### Q3. Common Git commands

```
git init           # Initialize a new Git repository
git clone <url>    # Copy repository from remote to local
git status         # Show modified/untracked files
git add .          # Stage all changes
git commit -m "msg" # Save a snapshot with a message
git log --oneline  # Show commit history in short form
git branch         # List branches
git checkout -b <branch>  # Create + switch to new branch
git merge <branch>         # Merge branch into current
git push origin main       # Push local commits to GitHub
git pull                   # Fetch + merge changes from remote
git fetch                  # Only download changes (no merge)
```

**💡 Pro Tip:** Mention `git commit -am "msg"` as a shortcut for tracked files.

### Q4. Difference between Git and GitHub?

* **Git:** Local VCS tool managing code versions.
* **GitHub:** Cloud hosting service with collaboration features.
  **Interview Edge:** Mention alternatives like GitLab, Bitbucket.

### Q5. What is a repository?

* **Local repository:** Exists on your machine (`git init`).
* **Remote repository:** Hosted on GitHub for collaboration.
  **💡 Pro Tip:** Highlight local vs remote repos.

### Q6. What is a commit?

A commit is a snapshot of code at a point in time, identified by SHA hash, author, timestamp, and message.
**💡 Pro Tip:** Clear commit messages help track changes.

## 📌 Section 2: Branching & Merging

### Q7. What is a branch?

A branch is a parallel line of development, allowing features without affecting main.
**💡 Pro Tip:** Feature branches prevent breaking production code.

### Q8. What is a merge conflict? How do you resolve it?

Occurs when two branches modify the same code.
**Steps:**

1. Open file and check conflict markers.
2. Decide correct changes or combine.
3. Save → `git add` → `git commit`
   **💡 Pro Tip:** Resolve conflicts quickly in team projects.

### Q9. Difference between `git merge` and `git rebase`

* **Merge:** Combines histories, keeps non-linear commits.
* **Rebase:** Replays commits on another branch, making history linear.
  **💡 Pro Tip:** Merge for collaboration, rebase for personal branches.

### Q10. What is a fast-forward merge?

Occurs when no new commits exist on target branch; branch pointer moves ahead without merge commit.
**💡 Pro Tip:** Fast-forward keeps history simple.

### Q11. What is a detached HEAD?

Git points directly to a commit, not a branch. Commits won’t belong to any branch unless you create one.
**💡 Pro Tip:** Used for experiments or reviewing older commits.

## 📌 Section 3: Commands

### Q12. Difference between `git pull` and `git fetch`

* **git fetch:** Downloads commits from remote into remote-tracking branches but doesn’t merge.
* **git pull:** Fetch + merge into current branch.

### Q13. What is `git stash`?

Temporarily saves uncommitted changes and resets working directory.
**Example:**

```
git stash
# switch branch
# fix bug
git stash pop
```

## 📌 Section 4: Staging & Workflow

### Q14. What is `git add` and why?

Stages changes from working directory to staging area. Git uses 3 stages: Working Directory → Staging → Repository.

### Q15. Do we always need `git add .` before commit?

No. For tracked files: `git commit -am "msg"`. For new/untracked files: `git add` is mandatory.

### Q16. What is `.gitignore`?

File listing files/folders Git should ignore (logs, build files, secrets).

### Q17. Difference between `git reset`, `git revert`, and `git checkout`

* **reset:** Moves HEAD back, possibly deleting commits.
* **revert:** Creates a new commit undoing changes.
* **checkout:** Switch branches or restore files.
  **💡 Pro Tip:** Prefer `revert` in teams to preserve history.

## 📌 Section 5: Remote Operations

### Q18. What is a remote in Git?

Reference to a hosted repository (usually GitHub). Default name = `origin`.

### Q19. How to push a branch to GitHub?

```
git push origin branch-name
# First time:
git push -u origin branch-name  # sets upstream tracking
```

### Q20. Difference between fork and clone?

* **Fork:** Copies repository to your GitHub account.
* **Clone:** Copies repository to local machine.

### Q21. What is a Pull Request (PR)?

Request to merge code into another branch on GitHub, allows review, discussion, and approval.

## 📌 Section 6: Tags & Releases

### Q22. What is a Git tag?

Label pointing to a commit, often for releases (v1.0.0).

### Q23. Difference between lightweight and annotated tags?

* **Lightweight:** Simple pointer.
* **Annotated:** Stores metadata (tagger, date, message).

### Q24. Create and push a tag

```
git tag -a v1.0.0 -m "First release"
git push origin v1.0.0
```

### Q25. Delete a tag

```
# Local
git tag -d v1.0.0
# Remote
git push --delete origin v1.0.0
```

### Q26. See commits between tags

```
git log v1.0.0..v2.0.0 --oneline
```

## 📌 Section 7: Advanced & Best Practices

### Q27. What is GitHub Actions?

CI/CD automation tool inside GitHub for workflows (build, test, deploy) triggered on events (push, PR).

### Q28. GitHub Flow vs Git Flow

* **GitHub Flow:** Simple → branch → PR → merge main.
* **Git Flow:** Structured → main, develop, feature, release, hotfix branches.
  **💡 Pro Tip:** GitHub Flow for startups, Git Flow for enterprise.

### Q29. Handling large files in GitHub

Use **Git LFS** (Large File Storage) for binaries outside Git history.

### Q30. Difference between main and origin/main

* **main:** Local branch.
* **origin/main:** Remote-tracking branch.

### Q31. Best practices with Git in teams

* Clear commit messages
* Feature branches
* Protect main branch
* Resolve conflicts early
* PRs for review
* Integrate GitHub Actions for CI/CD
