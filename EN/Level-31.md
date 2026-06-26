# Bandit Level 30 → 31

## Objective
Clone another Git repository. Neither the commit history nor other branches reveal the password this time. Find it in a git tag.

## Solution
Clone the repo, list the tags, and inspect the one with a suspicious name.

## Commands Used
```bash
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo
cd repo
ls
git tag
git show secret
```

## What I Learned

### git tag
Tags are named references to specific commits — used to mark releases (e.g., `v1.0`, `release-final`). They are separate from branches and from commit history.

```bash
git tag        # list all tags
git show TAG   # show the content of a tag
```

### Tags as a Secret Storage Vector
If a password or secret was committed and tagged at a specific version, the tag persists even if the commit content is later changed. `git show secret` revealed the raw content of the tag — which turned out to be the password.

### Comprehensive Git Audit
A complete Git security audit must check:
1. **Commit history** (`git log -p`)
2. **All branches** (`git branch -a`)
3. **All tags** (`git tag` + `git show`)

This level completes the trilogy by introducing tags as the third hiding place.

## Conclusion
The `secret` tag contained the password for the next level.
