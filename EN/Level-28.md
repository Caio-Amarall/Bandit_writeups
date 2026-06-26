# Bandit Level 27 → 28

## Objective
Clone a Git repository from the server and find the password inside it.

## Solution
Use `git clone` with the SSH protocol to clone the repository, then read the README.

## Commands Used
```bash
git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo
cd repo
ls
cat README
```

## What I Learned

### Git Repositories as Attack Surfaces
Git acts like a remote library where developers store versions of code. Repositories sometimes contain hardcoded passwords, API keys, or sensitive configuration — especially in their history.

### git clone with SSH
The SSH URL format for cloning over a non-standard port:
```bash
git clone ssh://user@host:port/path/to/repo
```

This is an important syntax difference from the standard `git clone git@host:repo` shorthand.

### Why Security Teams Review Git Repos
Exposed or misconfigured Git repositories are a major source of credential leaks. Attackers routinely search GitHub, GitLab, and internal repos for secrets left in code.

## Conclusion
After cloning the repository and reading `README`, we found the password for the next level.
