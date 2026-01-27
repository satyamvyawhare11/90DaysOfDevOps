

## Day 04 – Linux Practice
**OS:** Ubuntu Linux

---

### Process Commands

**Command:**

```
ps aux | head
```

**What I saw:**
This command shows running processes. I saw many system processes. PID 1 was systemd.

---

**Command:**

```
pgrep sshd
```

**What I saw:**
It returned a number. That means ssh service is running.

---

### Service Commands (SSH)

**Command:**

```
systemctl status ssh
```

**What I saw:**
SSH service was active and running. No error shown.

---

**Command:**

```
systemctl list-units --type=service --state=running | head
```

**What I saw:**
Many services were running like ssh and cron.

---

### Log Commands

**Command:**

```
journalctl -u ssh | tail -n 10
```

**What I saw:**
Some ssh login logs were there. No issue found.

---

**Command:**

```
tail -n 20 /var/log/syslog
```

**What I saw:**
System messages and cron logs were shown.

---

### Small Troubleshooting Practice

**Problem:** SSH not working

**Steps I tried:**

```
systemctl status ssh
sudo systemctl restart ssh
pgrep sshd
journalctl -u ssh -xe
```

**Result:**
After restart, ssh was working fine.

---

### What I learned today

* ps shows running processes
* systemctl is used for services
* logs help find problems

---

### Commands used today

* ps
* pgrep
* systemctl
* journalctl
* tail

---
