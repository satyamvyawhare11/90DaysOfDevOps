# Day 22 – Git Basics Notes

## What is the difference between git add and git commit?

git add moves changes to the staging area.
git commit permanently saves those staged changes to the repository history.

## What does the staging area do?

The staging area allows you to choose exactly what changes should go into the next commit.
Git doesn’t commit directly so that you can control your commit content carefully.

## What information does git log show?

It shows commit ID, author name, date, and commit message.
It tells the history of the project.

## What is the .git/ folder?

The .git folder stores all version history and metadata.
If we delete it, the project is no longer a Git repository and all history is lost.

## Difference between working directory, staging area, and repository?

Working directory → where files are edited.
Staging area → where changes are prepared for commit.
Repository → permanent stored commit history.
