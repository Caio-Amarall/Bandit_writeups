# Bandit Level 25 → 26

## Objective
Log in as `bandit26`, but the shell for that user is not `/bin/bash` — it is a custom restricted program. Find a way to escape it.

## Solution
The custom shell opens the file `/etc/motd` using the `more` pager. If the terminal window is small enough, `more` enters interactive mode (showing `--More--`). From there, we can invoke `vi` and then escape to a real shell.

## Steps
1. **Make the terminal window very small** (shrink it vertically until only a few lines fit, or on Windows PowerShell use `Ctrl+` to zoom in until text doesn't fit).
2. Connect: `ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220`
3. `more` pauses at `--More--` because the text doesn't fit.
4. Press `v` to open `vi`.
5. In vi, set the shell: `:set shell=/bin/bash`
6. Escape to the shell: `:shell`

## Commands Used
```bash
ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220
# [resize terminal first so --More-- appears]
v
:set shell=/bin/bash
:shell
```

## What I Learned

### Restricted Shell Escape via more → vi
Many systems (ATMs, kiosks, restricted servers) run a program on top of the OS. If that program enters a "paused" viewing mode, hidden escape sequences can open an underlying shell.

### vi as an Escape Vector
`vi` (and `vim`) can execute shell commands from within the editor:
- `:shell` — opens a shell using the configured `$SHELL`
- `:set shell=/bin/bash` — overrides the shell to use

This makes `vi` a classic **jailbreak tool** in CTFs and real-world restricted environments.

### Why Terminal Size Matters
`more` only enters interactive pager mode when the content doesn't fit the terminal. If the window is too large, it prints everything at once and exits — and we never get the `--More--` prompt.

## Conclusion
By exploiting the `more` pager and escaping into `vi`, we obtained a real bash shell as `bandit26`.
