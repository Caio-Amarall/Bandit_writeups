# Bandit Level 18 → 19

## Objective
Read the `readme` file in the home directory. The challenge: a modified `.bashrc` immediately logs us out the moment we connect via SSH.

## Solution
Append a command directly to the SSH login command. The command runs before `.bashrc` kicks us out, and we receive the output.

## Commands Used
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```

## What I Learned

### Executing Commands Over SSH Without Logging In
SSH allows appending a command in quotes at the end of the connection string. The remote server executes that command and returns the output — without ever dropping into an interactive shell:

```bash
ssh user@host -p port "command"
```

This technique is extremely useful in automation and in security scenarios where a restricted shell or logout trap is in place.

### Why This Works
The `.bashrc` modification only triggers when an interactive shell starts. By passing a command directly, we bypass the interactive shell and execute our command before `.bashrc` can run.

## Conclusion
By passing `"cat readme"` directly to the SSH command, we received the file contents — and the password for the next level — without ever being logged out.
