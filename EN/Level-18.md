# Bandit Level 17 → 18

## Objective
Two files are provided: `passwords.old` and `passwords.new`. The password for the next level is the only line that differs between the two files.

## Solution
Use `diff` to compare the two files and identify the changed line.

## Commands Used
```bash
ls
diff passwords.old passwords.new
```

## What I Learned

### diff Command
`diff` compares two files line by line and shows the differences:

```bash
diff file1 file2
```

Output symbols:
- `<` indicates a line only in file1
- `>` indicates a line only in file2
- Lines without symbols are identical

`diff` is heavily used in software development (code reviews, patch files) and in security (comparing config files before and after a change).

## Conclusion
Running `diff` immediately showed the one line that was different between the two files — that line was the password for the next level.
