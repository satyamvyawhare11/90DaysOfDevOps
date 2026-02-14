# Day 21 – Shell Scripting Cheat Sheet

This is my personal quick-reference guide after learning shell scripting from basics to mini projects.

---

## 🔹 Quick Reference Table

| Topic | Syntax | Example |
|-------|--------|---------|
| Variable | VAR="value" | NAME="DevOps" |
| Argument | $1, $2 | ./script.sh arg1 |
| If | if [ condition ]; then | if [ -f file ]; then |
| For loop | for i in list; do | for i in 1 2 3; do |
| Function | name() { ... } | greet() { echo "Hi"; } |
| Grep | grep pattern file | grep -i "error" log.txt |
| Awk | awk '{print $1}' file | awk -F: '{print $1}' /etc/passwd |
| Sed | sed 's/old/new/g' file | sed -i 's/foo/bar/g' config.txt |

---

## 🔹 Basics

### Shebang
```bash
#!/bin/bash
