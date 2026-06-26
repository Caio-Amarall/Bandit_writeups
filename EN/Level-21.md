# Bandit Level 20 → 21

## Objective
Use the `suconnect` setuid binary to get the next password. It connects to a port on localhost, reads a line, and if it matches the current level's password, it sends back the next password.

## Solution
We need two simultaneous connections: one to serve the current password on a port, and one to run `suconnect` against that same port.

## Commands Used

**Terminal 1 — start a listener serving the current password:**
```bash
echo 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO | nc -l -p 1234 &
```

**Terminal 2 (or same terminal after backgrounding):**
```bash
./suconnect 1234
```

## What I Learned

### Understanding suconnect
Running `./suconnect` with no arguments reveals its usage:
```
./suconnect <port>
```
It connects to the specified port, reads a line, and checks if it matches the current level's password. If correct, it sends back the next password.

### nc -l (Listen Mode)
`nc -l -p PORT` starts Netcat in **listen mode** — it waits for an incoming connection on the specified port and sends whatever data it receives (or was piped into it):
```bash
echo "data" | nc -l -p 1234
```

### Background Processes with &
Appending `&` to a command runs it in the background, freeing the terminal for the next command:
```bash
command &
```

### Two-Process Coordination
This level introduces the concept of coordinating two processes:
1. A **server** (listener) providing the password
2. A **client** (`suconnect`) verifying and exchanging it

This pattern is fundamental to understanding how networked services and authentication work.

## Conclusion
After setting up the listener and running `suconnect`, the binary verified the password and returned the next one.
