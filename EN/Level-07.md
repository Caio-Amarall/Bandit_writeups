# Bandit Level 6 → 7

## Objective
Find the password file somewhere on the entire server (not just the home directory). We don't know the directory or filename, but we know the file's properties:
- Owned by user `bandit7`
- Owned by group `bandit6`
- 33 bytes in size

## Solution
Use `find` starting from the root `/` directory with owner and group filters to locate the file.

## Commands Used
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

> **Tip:** Adding `2>/dev/null` suppresses permission-denied errors, making the output much cleaner.

## What I Learned

### Searching the Entire Filesystem
Using `/` as the starting point tells `find` to search the entire filesystem from the root:
```bash
find / ...
```

### New find Options

| Option | Description |
|--------|-------------|
| `-user bandit7` | Match files owned by a specific user |
| `-group bandit6` | Match files belonging to a specific group |

### Suppressing Permission Errors
`2>/dev/null` redirects error messages (file descriptor 2) to `/dev/null` (discarded), so only valid results are shown.

## Conclusion
After finding and reading the file, we obtained the password for the next level.
