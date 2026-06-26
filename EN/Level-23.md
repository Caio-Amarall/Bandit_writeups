# Bandit Level 22 → 23

## Objective
Another cron job in `/etc/cron.d/`. This time, the script uses an MD5 hash of the current username to determine the name of the temp file where it stores the password. We need to figure out that filename.

## Solution
Read the cron script to understand its logic, then replicate the hash calculation ourselves to derive the temp file path.

## Commands Used
```bash
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
cat /tmp/<hash>
```

## What I Learned

### Reading Scripts to Understand Logic
Instead of guessing, we read the actual script to understand exactly how the temp filename is constructed. The script runs:
```bash
echo I am user $myname | md5sum | cut -d ' ' -f 1
```
where `$myname` is the username. We substitute `bandit23` to get the hash ourselves.

### md5sum
`md5sum` computes the MD5 hash of its input. Though MD5 is broken for cryptographic purposes, it is still widely used for checksums and file identification.

### cut Command
`cut -d ' ' -f 1` splits the output by space (`-d ' '`) and returns only the first field (`-f 1`) — the hash itself, without the trailing filename `md5sum` appends.

### Security Relevance
Predictable temp file names based on username or other known inputs can be calculated ahead of time. This level shows why randomness is critical when generating sensitive file paths.

## Conclusion
By calculating the hash ourselves, we derived the temp file path and read the password for the next level.
