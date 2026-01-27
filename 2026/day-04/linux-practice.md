

---

## Day 04 – Linux Practice (Hand Written)
**System:** Linux (Ubuntu)

---

### Process Checks

**Command used**

```
ps aux
```

**Note:**
This command shows all running processes on the system.

---

**Command used**

```
top
```

**Note:**
This command shows running processes in real time and CPU usage.

---

### Service Checks

**Command used**

```
systemctl status ssh
```

**Note:**
This shows if the ssh service is running or stopped.

---

**Command used**

```
systemctl list-units --type=service
```

**Note:**
This shows all services managed by systemd.

---

### Log Checks

**Command used**

```
journalctl -u ssh
```

**Note:**
This command shows logs related to ssh service.

---

**Command used**

```
tail -n 50 /var/log/syslog
```

**Note:**
This shows the last 50 lines of system log.

---

### Small Troubleshooting Practice

**Problem:** ssh service not working

**Steps I followed**

```
systemctl status ssh
journalctl -u ssh
sudo systemctl restart ssh
```

**Result:**
ssh service started working after restart.

---

### What I learned

* `ps` and `top` are used to check running processes
* `systemctl` is used to manage services
* `journalctl` and `tail` are used to check logs

---

### Commands practiced today

* ps aux
* top
* systemctl status
* systemctl list-units
* journalctl
* tail

---

