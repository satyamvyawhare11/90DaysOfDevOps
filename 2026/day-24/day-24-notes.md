# Day 24 – Advanced Git: Merge, Rebase, Stash & Cherry Pick

## Task 1: Git Merge

### Fast-Forward Merge
A fast-forward merge happens when the main branch has no new commits since the feature branch was created. Git simply moves the main pointer forward.

### Merge Commit
Git creates a merge commit when both branches have new commits. It combines histories and creates a new commit tying them together.

### What is a Merge Conflict?
A merge conflict happens when the same line in the same file is modified in two branches. Git cannot decide which change to keep, so manual resolution is required.

---

## Observations from Merge Practice

- When merging feature-login without new commits on main → Fast-forward
- When main had new commits before merging feature-signup → Merge commit created
- When editing the same line on both branches → Conflict occurred and required manual resolution

---

## Task 2: Git Rebase

### What Does Rebase Do?
Rebase moves your branch’s commits and replays them on top of another branch. It rewrites commit history.

### How History Looks
- Merge → Shows branching structure in graph
- Rebase → Creates a clean, linear history

### Why Never Rebase Shared Commits?
Rebasing changes commit hashes. If others already pulled those commits, rewriting history causes confusion and conflicts.

### When to Use Rebase vs Merge?

Use rebase:
- For clean local history
- Before merging a feature branch
- For linear commit structure

Use merge:
- For shared branches
- When preserving history matters
- In team collaboration workflows

---

## Task 3: Squash vs Regular Merge

### Squash Merge
Squash merge combines all feature branch commits into a single commit before merging.

### Observation
After squash merge → Only one commit added to main.
After regular merge → All commits preserved.

### When to Use Squash?
- When feature branch has many small commits
- When you want a clean commit history

### Trade-Off
Squashing removes detailed commit history from the feature branch.

---

## Task 4: Git Stash

### What is Stash?
Stash temporarily saves uncommitted changes so you can switch branches safely.

### stash pop vs stash apply

git stash pop → Applies changes and removes stash from list  
git stash apply → Applies changes but keeps stash in list  

### Real-World Use
- Urgent bug fix while working on feature
- Quick branch switching without committing half-finished work

---

## Task 5: Cherry Pick

### What Does Cherry-Pick Do?
Cherry-pick copies a specific commit from one branch and applies it to another.

### When to Use Cherry-Pick?
- Hotfix from feature branch to main
- Applying selective commits without merging entire branch

### What Can Go Wrong?
- Conflicts during cherry-pick
- Duplicate commits if not handled carefully
- History confusion if overused

---

# Key Commands Practiced

git merge <branch>
git rebase <branch>
git merge --squash <branch>
git stash
git stash list
git stash pop
git stash apply
git cherry-pick <commit-hash>
git log --oneline --graph --all

---

# What I Learned

- Merge preserves history, rebase rewrites it
- Squash helps maintain clean history
- Stash is powerful for context switching
- Cherry-pick is useful but must be used carefully
- Understanding Git graph is critical for debugging history
