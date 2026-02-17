# Day 25 – Git Reset vs Revert & Branching Strategies

---

## Task 1 – Git Reset (Hands-On Observations)

### What is the difference between --soft, --mixed, and --hard?

**git reset --soft**
- Moves HEAD backward
- Keeps changes staged
- Useful when you want to edit the last commit

**git reset --mixed**
- Moves HEAD backward
- Unstages changes
- Keeps changes in working directory
- Default reset mode

**git reset --hard**
- Moves HEAD backward
- Deletes changes from working directory
- Completely discards commits and changes

---

### Which one is destructive and why?

`--hard` is destructive because it permanently deletes uncommitted changes from the working directory.

---

### When would you use each one?

- `--soft` → Fix commit message or combine commits
- `--mixed` → Rework staged changes
- `--hard` → Discard local mistakes completely

---

### Should you use git reset on pushed commits?

No. Reset rewrites history.  
If the commit is already pushed, it can break other collaborators' history.

---

## Task 2 – Git Revert (Hands-On Observations)

### What happens when reverting a middle commit?

- Git creates a new commit
- The original commit remains in history
- Its changes are reversed by the new commit

---

### How is git revert different from git reset?

- `git reset` removes commits from history
- `git revert` keeps history and adds a new commit to undo changes

---

### Why is revert safer for shared branches?

Because it does not rewrite history.  
It preserves the commit log and avoids conflicts for collaborators.

---

### When would you use revert vs reset?

Use `reset` for local cleanups.  
Use `revert` for production fixes or shared branches.

---

## Task 3 – Reset vs Revert Comparison

| Feature | git reset | git revert |
|----------|------------|------------|
| What it does | Moves branch pointer backward | Creates new commit to undo changes |
| Removes commit from history? | Yes | No |
| Safe for shared branches? | No | Yes |
| Best used for | Local history cleanup | Undoing changes in shared repos |

---

## Task 4 – Branching Strategies

### GitFlow

How it works:
- Separate branches: main, develop, feature, release, hotfix
- Structured release cycle

Used in:
- Large teams
- Enterprise projects

Pros:
- Clear release structure
- Organized workflow

Cons:
- Complex
- Heavy process overhead

---

### GitHub Flow

How it works:
- Single main branch
- Feature branches merged via Pull Requests

Used in:
- Startups
- Continuous deployment teams

Pros:
- Simple
- Fast shipping

Cons:
- Less structured for big release cycles

---

### Trunk-Based Development

How it works:
- Everyone commits to main
- Short-lived branches only

Used in:
- High CI/CD environments
- Large tech companies

Pros:
- Fewer merge conflicts
- Faster integration

Cons:
- Requires strong testing automation

---

## Strategic Thinking

Startup shipping fast → GitHub Flow  
Large team with scheduled releases → GitFlow  
High automation culture → Trunk-Based Development  

---

## Key Takeaways

- Reset rewrites history.
- Revert preserves history.
- Never rewrite shared branch history.
- Branching strategy depends on team size and release model.
- `git reflog` can recover lost commits after reset.
