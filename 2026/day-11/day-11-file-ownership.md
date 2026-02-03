# Day 11 – File Ownership Challenge

Today I practiced file and directory ownership using chown and chgrp.
This helped me understand how Linux controls access at user and group level.

## Files & Directories Created
- devops-file.txt
- team-notes.txt
- project-config.yaml
- app-logs/
- heist-project/
- bank-heist/

## Ownership Changes

- devops-file.txt: ubuntu → tokyo → berlin
- team-notes.txt: group changed to heist-team
- project-config.yaml: professor:heist-team
- app-logs/: berlin:heist-team
- heist-project/: professor:planners (recursive)
- bank-heist files:
  - access-codes.txt → tokyo:vault-team
  - blueprints.pdf → berlin:tech-team
  - escape-plan.txt → nairobi:vault-team

## Commands Used
- ls -l
- chown
- chgrp
- chown owner:group
- chown -R
- useradd
- groupadd

## What I Learned
- Owner and group control file access
- chown can change both owner and group
- Recursive ownership is important for project directories
