# Day 19 – Log Rotation, Backup & Crontab

## Scripts Created

### 1. log_rotate.sh
- Compresses .log files older than 7 days
- Deletes .gz files older than 30 days
- Takes log directory as argument

Example:
./log_rotate.sh /var/log/nginx

---

### 2. backup.sh
- Takes source and destination as arguments
- Creates timestamped .tar.gz archive
- Verifies backup creation
- Deletes backups older than 14 days

Example:
./backup.sh /home/ubuntu/scripts /home/ubuntu/backups

---

### 3. maintenance.sh
- Calls log rotation
- Calls backup
- Logs output to maintenance.log
- Designed to run using cron

Cron Example (Daily 1 AM):
0 1 * * * /home/ubuntu/scripts/maintenance.sh

---

## What I Learned

- Automating repetitive server tasks
- Managing log lifecycle properly
- Writing structured scripts with functions
- Using cron for scheduling automation
- Importance of error handling

This felt like real DevOps work, not just scripting practice.
