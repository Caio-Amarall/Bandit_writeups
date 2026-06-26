# Bandit Level 4 → 5

## Objective
Among several files in the `inhere` directory, find the only one that contains human-readable text (ASCII). That file holds the password.

## Solution
Use the `file` command to check the type of every file in the directory at once. The one identified as ASCII text is our target.

## Commands Used
```bash
ls
cd inhere/
ls -la
file ./*
cat ./-file07
```

## What I Learned

### Identifying Human-Readable Files
The `file` command reads the content of a file and reports its type (ASCII text, binary data, etc.).

Using `*` as a wildcard applies the command to **all files** in the current directory:
```bash
file ./*
```

This lets us quickly identify which file contains readable text without opening each one individually.

## Conclusion
After running `file ./*`, only `-file07` was identified as ASCII text. Reading it gave us the password for the next level.
