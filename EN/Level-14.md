# Bandit Level 13 → 14

## Objective
There is no password for this level. Instead, a private SSH key (`sshkey.private`) is provided. We need to use it to log in as `bandit14` and then read the password file at `/etc/bandit_pass/bandit14`.

## Solution
Copy the private key content, save it locally, set the correct permissions, and use it to SSH in as bandit14.

## Commands Used
```bash
cat sshkey.private
# Copy the output to a local file named bandit14.key
ssh -i bandit14.key bandit14@bandit.labs.overthewire.org -p 2220
cat /etc/bandit_pass/bandit14
```

> **Windows PowerShell note:** On Linux, you would run `chmod 600 bandit14.key` to restrict the key's permissions. On Windows PowerShell, `chmod` does not work the same way. Instead, right-click the file → Properties → Security → set permissions manually so only your user has read access. SSH will refuse to use a key file with overly permissive settings.

## What I Learned

### SSH -i Flag (Identity File)
The `-i` flag tells SSH to use a specific private key file for authentication instead of a password:
```bash
ssh -i keyfile user@host -p port
```

### Private Key Authentication
SSH key-based authentication works as a key pair:
- **Private key**: stays on your machine (never share it)
- **Public key**: stored on the server

When you connect, SSH proves you own the private key without transmitting it. This is more secure than passwords.

### nano
`nano` is a simple terminal text editor used to create or edit files:
```bash
nano filename
```

## Conclusion
After connecting with the private key, we read `/etc/bandit_pass/bandit14` and obtained the password for the next level.
