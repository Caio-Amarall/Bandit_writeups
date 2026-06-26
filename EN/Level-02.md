# Bandit Level 1 → 2

## Objective
Read a file named `-` to find the password for the next level.

## Solution
We know the filename. The challenge is that a lone `-` is interpreted by most commands as "read from stdin" rather than as a filename. We need to explicitly tell the shell it's a file path.

## Commands Used
```bash
ls
cat ./-
```

## What I Learned

### Reading Files With Special Character Names
Running `cat -` alone does not work because the shell interprets `-` as "standard input", causing the terminal to hang waiting for keyboard input.

By prefixing with `./`, we tell the shell it is a file in the current directory, not a flag or stdin redirect:
```bash
cat ./-
```

## Conclusion
By specifying the file path explicitly, we can read it and obtain the password for the next level.
