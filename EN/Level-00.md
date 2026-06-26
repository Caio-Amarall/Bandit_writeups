# Bandit Level 0

## Objective
Connect to the challenge server using SSH.

## Solution
We have the following connection details:
- Host: bandit.labs.overthewire.org
- Port: 2220
- Username: bandit0
- Password: bandit0

## Commands Used
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## What I Learned

### SSH
SSH (Secure Shell) is a program that establishes a secure connection to a remote machine and executes commands on it. The basic syntax is:

```
ssh [user]@[server] [options]
```

The `-p` flag specifies the port to connect to. The default SSH port is 22, but this server uses 2220.

> **Note:** I am using Windows PowerShell as my terminal. This will be relevant in future levels where some Linux-specific commands behave differently.

## Conclusion
Successfully connected to the server using SSH. Moving on to the next level.
