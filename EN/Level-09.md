# Bandit Level 8 → 9

## Objective
The password in `data.txt` is the only line that appears exactly once. All other lines are duplicated.

## Solution
Use `sort` to group identical lines together, then `uniq -u` to keep only lines that appear once.

## Commands Used
```bash
ls
sort data.txt | uniq -u
```

## What I Learned

### sort Command
`sort` arranges lines alphabetically, grouping identical lines next to each other. This is a required prerequisite for `uniq` to work correctly.

### uniq Command
`uniq` removes or filters duplicate **adjacent** lines. Because it only compares neighbouring lines, it must be used after `sort`.

### The `-u` Flag
`-u` (unique) tells `uniq` to print **only** lines that appear exactly once — discarding any duplicates.

### The Pipe `|`
The pipe character `|` takes the output of the left command and feeds it as input to the right command, allowing commands to be chained on one line.

## Conclusion
Combining `sort` and `uniq -u` filtered out all duplicates and returned the single unique line — the password for the next level.
