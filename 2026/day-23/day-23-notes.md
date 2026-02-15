# Day 23 – Git Branching & Working with GitHub

## What is a Branch in Git?
A branch is a separate line of development in Git. It allows you to work on features, fixes, or experiments without affecting the main branch.

---

## Why Do We Use Branches Instead of Committing Everything to main?
- Keeps the main branch stable
- Allows safe experimentation
- Makes team collaboration easier
- Prevents breaking production code
- Enables feature-based workflow

---

## What is HEAD in Git?
HEAD is a pointer that refers to the current branch and commit you are working on. When you switch branches, HEAD moves to that branch.

---

## What Happens to Your Files When You Switch Branches?
- Git updates your working directory
- Files change to match that branch’s latest commit
- Commits unique to other branches disappear
- The branch you switch to becomes active

---

# Branching Commands Practiced

List all branches:
git branch

Create a new branch:
git branch feature-1

Switch to feature-1:
git switch feature-1

Create and switch in one command:
git switch -c feature-2

Make a commit on feature-1:
git add .
git commit -m "Added changes in feature-1"

Switch back to main:
git switch main

Delete a branch:
git branch -d feature-2

---

# Push to GitHub

Add remote:
git remote add origin <repo-url>

Push main branch:
git push -u origin main

Push feature branch:
git push -u origin feature-1

---

## What is the Difference Between origin and upstream?

origin → Your repository on GitHub  
upstream → The original repository you forked from  

---

## What is the Difference Between git fetch and git pull?

git fetch → Downloads changes but does not merge them  
git pull → Downloads changes and merges them automatically  

---

## Clone vs Fork

Clone → Copy a repository to your local machine  
Fork → Create your own copy of someone else's repository on GitHub  

After forking, you can keep your fork in sync by adding the original repository as upstream and pulling updates.

---

# What I Learned

- Branching allows isolated development
- HEAD tracks the current branch
- GitHub enables collaboration using remote branches
- Switching branches changes your working directory state
- Fetch and pull are different in how they handle merging
