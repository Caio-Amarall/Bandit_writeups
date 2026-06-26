# Bandit Level 32 → 33

## Objective
We are dropped into an "UPPERCASE SHELL" — every command we type is converted to uppercase before execution. Since Linux commands are case-sensitive and always lowercase, nothing works. Escape the restricted shell.

## Solution
Use `$0`, a special shell variable that expands to the name of the current shell. Since `$0` is not a letter, it is not converted to uppercase. Typing `$0` spawns a real shell.

## Commands Used
```bash
$0
cat /etc/bandit_pass/bandit33
```

## What I Learned

### $0 — The Shell's Own Name
`$0` is a special shell variable that holds the name (or path) of the currently running shell or script. When typed at a restricted prompt, it effectively re-invokes the shell — which in this case is `/bin/sh` or `/bin/bash`, spawning a real, unrestricted shell.

```bash
echo $0   # → /bin/bash (or sh, etc.)
$0        # → opens a new shell
```

### Why This Works Against the UPPERCASE Shell
The uppercase filter only processes alphabetic characters. `$0` contains no letters — just a `$` and `0` — so it passes through unmodified and is executed normally by the underlying shell.

### Restricted Shell Escapes
This level is a practical example of **restricted shell escape**, a real technique used in:
- Penetration testing (escaping jailed environments)
- CTF challenges
- Security assessments of kiosk systems or limited-access terminals

## Conclusion
By typing `$0`, we escaped the uppercase shell and gained a real bash prompt. Reading `/etc/bandit_pass/bandit33` gave us the final password — completing all Bandit levels!

---

🎉 **All 33 levels completed!** This journey covered Linux fundamentals, networking, cryptography, automation, git internals, and multiple privilege escalation techniques.
