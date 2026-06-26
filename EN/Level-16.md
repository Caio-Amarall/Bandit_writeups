# Bandit Level 15 → 16

## Objective
Submit the current level's password to `localhost` on port `30001` using SSL/TLS encryption to receive the next password.

## Solution
Port 30001 uses SSL/TLS, so plain Netcat won't work. We need to use `openssl s_client`, which acts like Netcat but can speak the SSL/TLS protocol.

## Commands Used
```bash
openssl s_client -connect localhost:30001
```
Then type (or paste) the current level's password and press Enter.

## What I Learned

### openssl s_client
`openssl s_client` is a command-line tool that opens an SSL/TLS connection to a host, similar to Netcat but capable of encrypted communication. It is invaluable for:
- Testing SSL/TLS services
- Inspecting certificates
- Sending data to HTTPS or other TLS-protected ports

```bash
openssl s_client -connect host:port
```

### Why Netcat Fails Here
`nc` sends plain-text data. Services protected by SSL/TLS perform a cryptographic handshake before accepting data — `nc` cannot do this, so the connection fails. `openssl s_client` handles the handshake transparently.

### Security Relevance
Understanding TLS is critical in security work. Many vulnerabilities (e.g., POODLE, Heartbleed) target the TLS handshake or implementation weaknesses.

## Conclusion
After connecting with `openssl s_client` and submitting the current password, the server returned the password for the next level.
