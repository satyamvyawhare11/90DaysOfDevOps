# Day 09 – Linux User & Group Management Challenge

Today I practiced creating users, groups, and managing permissions.
This helped me understand how teams work on shared servers.

## Users & Groups Created

Users:
- tokyo
- berlin
- professor
- nairobi

Groups:
- developers
- admins
- project-team

## Group Assignments

- tokyo → developers, project-team
- berlin → developers, admins
- professor → admins
- nairobi → project-team

## Directories Created

- /opt/dev-project
  - Group: developers
  - Permissions: 775

- /opt/team-workspace
  - Group: project-team
  - Permissions: 775

## Commands Used

- useradd, passwd
- groupadd
- usermod -aG
- groups
- mkdir, chgrp, chmod
- sudo -u username command

## What I Learned

- Users need correct group access to work on shared folders
- Permissions (rwx) control who can read, write, or execute
- Group-based access is very common in real servers
