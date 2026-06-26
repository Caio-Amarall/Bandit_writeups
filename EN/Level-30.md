# Bandit Level 29 → 30

## Objective
Clone another Git repository. The README says "no passwords in production!" but the password may exist in a different branch.

## Solution
Clone the repo, list all branches (including remote ones), and check out the development branch where the password may not have been cleaned up yet.

## Commands Used
```bash
git clone ssh://bandit29-git@bandit.labs.overthewire.org:2220/home/bandit29-git/repo
cd repo
git branch -a
git checkout remotes/origin/dev
cat README.md
```

> **Note:** The original PT_BR writeup had a typo — `removes/origin/dev` instead of `remotes/origin/dev`.

## What I Learned

### git branch -a
Lists **all** branches, including remote-tracking branches:
```bash
git branch -a
```
Remote branches are prefixed with `remotes/origin/`.

### git checkout (switching branches)
```bash
git checkout remotes/origin/dev
```
Switches to the `dev` branch on the remote origin, where developers often leave "work in progress" code — including secrets that haven't been sanitized for production.

### Why Branches Are a Security Risk
Developers frequently use feature or dev branches to test code and may commit credentials "temporarily" — then forget to clean them before merging or leaving the branch public. Security audits should always check **all** branches, not just `main`.

## Conclusion
The `dev` branch contained the password in `README.md` — it hadn't been redacted like the production branch. We used it to access the next level.
