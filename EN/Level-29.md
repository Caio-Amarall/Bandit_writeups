# Bandit Level 28 → 29

## Objective
Clone another Git repository. The `README.md` shows the password as redacted (`xxxxxxx`). Recover the original value from the commit history.

## Solution
Clone the repo, inspect the git log with patch output (`-p`) to see what was changed in previous commits — including the value that was later censored.

## Commands Used
```bash
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo
cd repo
ls
git log -p
```

## What I Learned

### git log -p (Patch Mode)
`git log` shows the commit history. Adding `-p` (patch) shows the **diff** for each commit — the exact lines added and removed:
- Lines starting with `+` were added
- Lines starting with `-` were removed

This means if someone committed a password and then "removed" it in a later commit, `git log -p` will show both the addition and the removal — revealing the original value.

### Why Git History Is Dangerous
Even after removing sensitive data in a new commit, the data lives forever in the git history. The only way to truly remove it is to rewrite history (e.g., `git filter-branch` or `git filter-repo`), which is complex and breaks the history for all collaborators.

This is a critical concept in **secret management** and **DevSecOps**.

## Conclusion
By inspecting the commit history with `git log -p`, we found the password before it was redacted, and used it to access the next level.
