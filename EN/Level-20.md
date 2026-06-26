# Bandit Level 19 → 20

## Objective
Use the `bandit20-do` setuid binary in the home directory to read the password for bandit20.

## Solution
The binary runs with `bandit20`'s permissions. We use it to execute `cat` on the bandit20 password file, which we normally cannot read as bandit19.

## Commands Used
```bash
ls -l
./bandit20-do ls /etc/bandit_pass
./bandit20-do cat /etc/bandit_pass/bandit20
```

## What I Learned

### SETUID (Set User ID)
Normally, a program runs with the permissions of the user who executes it. A file with the **SETUID bit** set runs with the permissions of the file's **owner** instead.

In this case:
- We are logged in as `bandit19`
- `bandit20-do` is owned by `bandit20` and has the SETUID bit set
- Running `./bandit20-do <command>` executes `<command>` as `bandit20`

You can identify SETUID binaries with `ls -l` — they show an `s` instead of `x` in the owner execute field:
```
-rwsr-xr-x  ...  bandit20-do
```

### Security Relevance
SETUID misconfigurations are a classic **Linux privilege escalation** vector. Finding writable or exploitable SETUID binaries is a core skill in CTFs and real-world pentesting.

## Conclusion
Using `./bandit20-do cat /etc/bandit_pass/bandit20`, we read the password file with elevated permissions and obtained the password for the next level.
