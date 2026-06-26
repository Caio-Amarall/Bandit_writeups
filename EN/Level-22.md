# Bandit Level 21 → 22

## Objective
Investigate the `/etc/cron.d/` directory to understand how an automated job is leaking the password for the next level.

## Solution
Read the cron job configuration to find which script it runs, then read that script to understand what it does. The script writes the password to a world-readable temporary file.

## Commands Used
```bash
ls -l
cd /etc/cron.d/
ls -la
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

## What I Learned

### Cron Jobs
Cron is the Linux task scheduler. Jobs defined in `/etc/cron.d/` run automatically at set intervals. Each line in a cron file follows the format:
```
* * * * *  user  command
```
(minute, hour, day-of-month, month, day-of-week)

### Insecure Temporary Files
The script creates a file in `/tmp` with a predictable name and writes the password into it with world-readable permissions. This is a classic misconfiguration:
- Temporary files storing sensitive data should use restricted permissions
- Predictable filenames in `/tmp` can be exploited (race conditions, symlink attacks)

### Security Relevance
Reviewing cron jobs is a standard step in privilege escalation. Misconfigured scripts running as privileged users are a common attack vector.

## Conclusion
After tracing the cron job → script → temp file chain, we read the password for the next level.
