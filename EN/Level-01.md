# Bandit Level 0 → 1

## Objective
Find a file called `readme` located in the home directory and use the password found inside to connect to the bandit1 server.

## Solution
We know the file location. We just need to list the directory contents and read the file.

## Commands Used
```bash
ls
cat readme
```

## What I Learned

### ls
The `ls` command lists files and folders in the current directory.
By default, it does not show hidden files. To list all files including hidden ones, permissions, and additional information, use:
```bash
ls -alps
```

### cat
The `cat` command reads and prints the content of a text file to the terminal.

## Conclusion
After reading the `readme` file, we obtain the password for the next level.
