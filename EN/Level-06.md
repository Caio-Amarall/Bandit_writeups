# Bandit Level 5 → 6

## Objective
Find a specific file somewhere inside the `inhere` directory that meets all of the following criteria:
- Human-readable
- 1033 bytes in size
- Not executable

## Solution
We know the base location and the file's properties. We can use `find` with multiple filters to locate it precisely.

## Commands Used
```bash
ls
cd inhere/
ls -la
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```

## What I Learned

### find Command Options
`find` is a powerful tool for locating files based on their attributes:

| Option | Description |
|--------|-------------|
| `-type f` | Only match regular files |
| `-size 1033c` | Match files exactly 1033 bytes (`c` = bytes) |
| `! -executable` | Exclude executable files (`!` negates the next condition) |

Combining these filters makes it easy to pinpoint a specific file even among thousands.

## Conclusion
After running the `find` command, only one file matched all criteria. Reading it gave us the password for the next level.
