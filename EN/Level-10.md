# Bandit Level 9 → 10

## Objective
The password is stored in `data.txt` among binary data. It is one of the few human-readable strings and is preceded by several `=` characters.

## Solution
Use `strings` to extract printable text from the binary file, then pipe to `grep` to filter for lines with `==`.

## Commands Used
```bash
ls
strings data.txt | grep "=="
```

## What I Learned

### strings Command
`strings` scans a file (even a binary one) and extracts sequences of printable characters. It filters out all the non-human-readable binary data, leaving only text.

This is a fundamental tool in reverse engineering and binary analysis.

### Combining strings and grep
By piping `strings` output to `grep "=="`, we further narrow the results to only lines that match the pattern described in the challenge — lines preceded by `=` signs.

## Conclusion
The combination `strings data.txt | grep "=="` returned just a few lines, one of which contained the password for the next level.
