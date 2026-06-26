# Bandit Level 26 → 27

## Objective
Still logged in as `bandit26` via the vi escape from the previous level. There is a `bandit27-do` setuid binary in the home directory. Use it to read the password for bandit27.

## Solution
Same approach as Level 19 → 20: use the SETUID binary to run a command as `bandit27`.

## Commands Used
```bash
ls
./bandit27-do cat /etc/bandit_pass/bandit27
```

## What I Learned

### SETUID Binary (revisited)
`bandit27-do` is owned by `bandit27` and has the SETUID bit set. Running it executes the specified command with `bandit27`'s permissions — allowing us to read files we normally cannot.

This level reinforces the privilege escalation concept from Level 19, applying it immediately after the shell escape from Level 25.

### Chaining Exploits
Levels 25 → 26 → 27 demonstrate **exploit chaining**: one vulnerability (restricted shell bypass via `more`+`vi`) unlocks access to a SETUID binary that escalates privileges further. This is exactly how real-world attack chains work.

## Conclusion
Reading the bandit27 password file via the SETUID binary gave us the password for the next level.
