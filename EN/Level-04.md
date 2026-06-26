# Bandit Level 3 → 4

## Objective
Find and read a hidden file inside the `inhere` directory to get the password for the next level.

## Solution
We know the directory name and that the file is hidden. Hidden files in Linux start with a `.` and are not shown by default with `ls`.

## Commands Used
```bash
ls
cd inhere/
ls -a
cat ./...Hiding-From-You
```

## What I Learned

### How to Show Hidden Files
Hidden files and directories in Linux start with a dot (`.`). The default `ls` command does not display them.

Use the `-a` flag to show **all** files, including hidden ones:
```bash
ls -a
```

For more details (permissions, owner, size), combine flags:
```bash
ls -la
```

## Conclusion
After using `ls -a`, the hidden file appeared and we were able to read it and find the password.
