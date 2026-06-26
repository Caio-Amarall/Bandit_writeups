# Bandit Level 14 → 15

## Objective
Submit the current level's password to `localhost` on port `30000` to receive the next password.

## Solution
Use `nc` (Netcat) to connect to localhost on port 30000 and send the current password. We can pipe the password directly from its file.

## Commands Used
```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

## What I Learned

### nc (Netcat)
Netcat is often called the "Swiss Army knife" of networking. It creates raw TCP/UDP connections, allowing you to send and receive data directly over the network.

Basic usage:
```bash
nc hostname port
```

Combined with a pipe, we can send data to a listening port without typing it manually:
```bash
echo "some data" | nc localhost 30000
```

### Why This Matters in Security
Netcat is a fundamental tool in penetration testing for:
- Creating reverse shells
- Port scanning (basic)
- Transferring files between machines
- Testing open ports and services

## Conclusion
After sending the current password to port 30000, the server responded with the password for the next level.
