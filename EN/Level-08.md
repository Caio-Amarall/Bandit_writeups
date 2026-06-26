# Bandit Level 7 → 8

## Objective
The password is stored in `data.txt` next to the word `millionth`. The file contains thousands of lines.

## Solution
Use `grep` to search for the specific word within the large file.

## Commands Used
```bash
ls
grep "millionth" data.txt
```

## What I Learned

### grep Command
`grep` searches for a specific pattern or word within a file and prints the matching line(s):
```bash
grep "pattern" filename
```

This is essential when dealing with large files where manual searching is impractical. `grep` can scan millions of lines in seconds.

## Conclusion
Running `grep "millionth" data.txt` returned the line containing the word alongside the password for the next level.
