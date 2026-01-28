# Linux Troubleshooting Runbook – Day 05

## Target Service
ssh (sshd)

## Environment
- OS: Ubuntu 24.04.3 LTS
- Kernel: 6.14.0-1018-aws
- Platform: AWS EC2

## Snapshot: CPU & Memory
Commands:
- pidof sshd
- ps -o pid,pcpu,pmem,comm -p <pid>
- free -h

Observations:
- sshd is running normally with expected parent and child processes
- CPU usage is negligible and stable
- Available memory is low (~247MB), indicating moderate memory pressure

## Snapshot: Disk & IO
Commands:
- df -h
- du -sh /var/log

Observations:
- Root filesystem usage is at 93%, which is a critical threshold
- /var/log size is moderate (134MB) and not the primary cause of disk usage

## Snapshot: Network
Commands:
- sudo ss -tulpn | grep :22
- curl -I http://localhost

Observations:
- SSH service is actively listening on port 22
- nginx responds successfully on localhost
- Network stack is functioning correctly

## Logs Reviewed
Commands:
- journalctl -u ssh -n 50
- tail -n 50 /var/log/auth.log

Observations:
- SSH service starts and restarts normally
- Successful key-based SSH logins observed
- No service crashes or authentication errors found

## Quick Findings
- SSH service is healthy and stable
- No CPU or network-related issues detected
- Disk space usage is the primary operational risk

## If This Worsens (Next Steps)
1. Identify large files and directories using:
   `du -xh / | sort -hr | head -20`
2. Clean unused packages, logs, or temporary files, or expand the root volume
3. Add swap memory or resize the instance to improve memory stability

## Resources
- man ps
- man df
- man journalctl
- man ss
- AWS EC2 storage best practices
