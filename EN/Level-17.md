# Bandit Level 16 → 17

## Objective
Find the correct port in the range 31000–32000 on localhost that speaks SSL/TLS and returns a private SSH key when we submit the current password.

## Solution
1. Use `nmap` to scan ports 31000–32000 and identify which ones are open and speak SSL.
2. Connect to the correct port using `openssl s_client` and submit the current password.
3. Save the returned private SSH key to a local file, set permissions, and use it to log in as bandit17.

## Commands Used
```bash
nmap -p 31000-32000 localhost
openssl s_client -connect localhost:31790
# [paste current password and press Enter]
# [copy the returned private key]
ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
```

## What I Learned

### nmap (Network Mapper)
`nmap` is the industry-standard tool for network discovery and security auditing. It can:
- Discover open ports on a host
- Identify running services and their versions
- Detect operating systems
- Map networks

```bash
nmap -p 31000-32000 localhost
```
`-p` specifies the port range to scan.

### Identifying the Right Port
Among all open ports in the range, only one will accept the SSL handshake AND return a private key. Others either don't speak SSL or echo back what you send. Testing each candidate with `openssl s_client` quickly narrows it down.

### Private Key Workflow (review)
Same as Level 13 → 14: save the key to a file, set restrictive permissions, then use `ssh -i`.

## Conclusion
After scanning with nmap, connecting to the correct SSL port with openssl, and saving the returned SSH key, we logged into the next level.
