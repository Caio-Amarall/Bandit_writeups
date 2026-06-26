# Bandit Level 2 → 3

## Objective
Read a file named `spaces in this filename` and find the password.

## Solution
We already have the filename. The challenge is that spaces in filenames cause the shell to interpret each word as a separate argument. We need to escape them.

## Commands Used
```bash
ls
cat ./spaces\ in\ this\ filename
```

## What I Learned

### Reading Files With Spaces in the Name
When a filename contains spaces, the shell splits it into multiple arguments. There are two ways to handle this:

1. **Escape each space** with a backslash `\`:
   ```bash
   cat ./spaces\ in\ this\ filename
   ```

2. **Wrap the name in quotes**:
   ```bash
   cat "./spaces in this filename"
   ```

Both approaches tell the shell to treat the entire string as a single filename.

## Conclusion
After reading the file, we obtain the password for the next level.
