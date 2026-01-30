# Day 07 – Linux File System & Scenario Practice

Today I learned where important things live in Linux and how to think during basic troubleshooting.
I focused more on understanding the flow, not remembering commands.

## Part 1: Linux File System Hierarchy

### /
- This is the root of Linux
- Everything starts from here
- I would use this when I want to understand full system structure

Command run:
ls -l /

---

### /home
- Home directory for normal users
- User files and configs are stored here
- I would use this when checking user files or scripts

Command run:
ls -l /home

---

### /root
- Home directory of root user
- Normal users cannot access it
- I would use this when working as root user

Command run:
ls -l /root

---

### /etc
- Configuration files are stored here
- Services read configs from this directory
- I would use this when checking or editing configs

Command run:
ls -l /etc

Example file:
cat /etc/hostname

---

### /var/log
- Log files are stored here
- Very important for debugging
- I would use this when service is failing

Command run:
ls -l /var/log

Largest log files:
du -sh /var/log/* 2>/dev/null | sort -h | tail -5

---

### /tmp
- Temporary files
- Files can be deleted after reboot
- I would use this for temporary testing

Command run:
ls -l /tmp

---

### /bin
- Basic Linux commands
- Commands like ls, cp, mv are here
- I would use this when system is in minimal mode

Command run:
ls -l /bin

---

### /usr/bin
- User commands are stored here
- Most commands are located here
- I would use this when checking command location

Command run:
ls -l /usr/bin

---

### /opt
- Optional or third-party software
- Used by custom applications
- I would use this when app is manually installed

Command run:
ls -l /opt

---

## Part 2: Scenario Based Practice

### Scenario 1: Service Not Starting

Problem: myapp service not starting after reboot

Step 1:
systemctl status myapp  
Why: Check if service is running or failed

Step 2:
journalctl -u myapp -n 50  
Why: Check recent error logs

Step 3:
systemctl is-enabled myapp  
Why: Check if service starts on boot

Step 4:
systemctl list-units --type=service  
Why: Confirm service exists

What I learned: Always check status first, then logs.

---

### Scenario 2: High CPU Usage

Problem: Server is slow

Step 1:
top  
Why: See live CPU usage

Step 2:
ps aux --sort=-%cpu | head -10  
Why: Find high CPU process

Step 3:
Note PID of top process  
Why: PID helps in further actions

What I learned: First identify, then decide action.

---

### Scenario 3: Finding Service Logs (docker)

Step 1:
systemctl status docker  
Why: Confirm service state

Step 2:
journalctl -u docker -n 50  
Why: Check recent logs

Step 3:
journalctl -u docker -f  
Why: Live log monitoring

What I learned: systemd logs are handled by journalctl.

---

### Scenario 4: Permission Denied Script

Problem: /home/user/backup.sh not running

Step 1:
ls -l /home/user/backup.sh  
Why: Check permissions

Step 2:
chmod +x /home/user/backup.sh  
Why: Add execute permission

Step 3:
ls -l /home/user/backup.sh  
Why: Verify permission

Step 4:
./backup.sh  
Why: Test script

What I learned: Script needs execute permission.

---

## Final Learning

- Linux file system has fixed structure
- Logs and configs are in specific places
- Troubleshooting is about steps, not speed
- Understanding flow is more important than commands
