# Day 10 – File Permissions & File Operations Challenge

Today I practiced creating files, reading them, and controlling access using Linux permissions.

## Files Created
- devops.txt
- notes.txt
- script.sh
- project/ (directory)

## Permission Changes

- script.sh
  - Before: not executable
  - After: executable using chmod +x

- devops.txt
  - Set to read-only for all users

- notes.txt
  - Permissions set to 640

- project/
  - Permissions set to 755

## Commands Used
- touch
- echo > file
- vim
- cat, head, tail
- chmod
- ls -l

## What I Learned
- Permissions control who can read, write, and execute files
- Scripts need execute permission to run
- chmod is a critical command for security
