# Day 26 – GitHub CLI (gh)

Today I learned how to use GitHub directly from the terminal using GitHub CLI (gh).
This helps avoid switching to the browser again and again.

---

## Task 1 – Install & Authenticate

I installed GitHub CLI and authenticated using:

gh auth login

After login, I verified:

gh auth status

### Authentication Methods Supported
- Browser login (recommended)
- Token-based authentication (PAT)
- SSH key authentication

---

## Task 2 – Working with Repositories

Create a new repo:

gh repo create test-gh-cli --public --source=. --remote=origin --push

Clone a repo:

gh repo clone owner/repo

List all my repos:

gh repo list

View repo details:

gh repo view

Open repo in browser:

gh repo view --web

Delete repo (careful):

gh repo delete repo-name

Observation:
Managing repos from terminal feels faster and cleaner.

---

## Task 3 – Issues

Create issue:

gh issue create --title "Test issue" --body "Created from terminal" --label bug

List issues:

gh issue list

View issue:

gh issue view <issue-number>

Close issue:

gh issue close <issue-number>

### How gh issue can be used in automation?

It can:
- Automatically create issues when a deployment fails
- Track errors from CI/CD pipelines
- Create incident reports via scripts

---

## Task 4 – Pull Requests

Create branch:

git checkout -b feature-cli-test

Make change and push:

git add .
git commit -m "Test CLI PR"
git push -u origin feature-cli-test

Create PR from terminal:

gh pr create --fill

List PRs:

gh pr list

View PR details:

gh pr view

Merge PR:

gh pr merge

### Merge Methods Supported
- merge
- squash
- rebase

### Reviewing Someone Else’s PR
You can:
- View PR details
- Check commits
- Leave comments
- Approve or request changes

All from terminal.

---

## Task 5 – GitHub Actions (Preview)

List workflow runs:

gh run list

View specific run:

gh run view <run-id>

### How useful in CI/CD?

- Monitor builds directly from terminal
- Trigger workflows
- Automate deployment checks
- Integrate into scripts

---

## Task 6 – Useful gh Commands

Raw API calls:

gh api

Create gist:

gh gist create file.txt

Create release:

gh release create v1.0

Create command alias:

gh alias set prc "pr create --fill"

Search repos:

gh search repos devops

---

## What I Learned

- GitHub CLI reduces context switching
- PRs and issues can be managed without browser
- gh is powerful for DevOps automation
- JSON output makes scripting easy
- It feels like managing GitHub as code
