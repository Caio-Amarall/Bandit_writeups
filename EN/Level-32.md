# Bandit Level 31 → 32

## Objective
Clone another Git repository. This time, instead of reading from it, we need to **push** a file to it. The server validates the push and reveals the password.

## Solution
Clone the repo, create the required file, add it to git, commit, and push.

## Commands Used
```bash
git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo
echo "May I come in?" > key.txt
git add key.txt
git commit -m "Add key file"
git push origin master
```

> **Windows PowerShell note:** To ensure ASCII encoding, use:
> ```powershell
> "May I come in?" | Out-File -FilePath key.txt -Encoding ascii
> ```

## What I Learned

### git add, commit, push
The standard git workflow for contributing changes:
```bash
git add filename      # stage the file
git commit -m "msg"   # create a commit with a message
git push origin branch # send the commit to the remote
```

### Write Access as an Attack Vector
If an attacker gains **write access** to a repository, they can push malicious scripts, backdoors, or configuration files. In CI/CD pipelines, pushed code is often automatically deployed — making repository write access a high-severity security risk.

### .gitignore
If files aren't being added, check `.gitignore` — the repo may be configured to exclude certain filenames or extensions. In this level, a `.gitignore` might block `*.txt` files, requiring `git add -f` to force-add.

## Conclusion
After pushing the required file, the remote server responded with the password for the next (final) level.
