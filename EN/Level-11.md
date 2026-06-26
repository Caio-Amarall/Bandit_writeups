# Bandit Level 10 → 11

## Objective
The password is stored in `data.txt`, which contains Base64-encoded data.

## Solution
Use the `base64` command with the decode flag to convert the encoded content back to readable text.

## Commands Used
```bash
ls
base64 -d data.txt
```

## What I Learned

### Base64 Encoding
Base64 is an encoding scheme that converts binary or text data into a string of ASCII characters (A-Z, a-z, 0-9, +, /). It is commonly used to transmit data safely over text-based protocols like email or HTTP headers.

It is **not** encryption — anyone can decode it.

### base64 Command
Linux includes a built-in `base64` command to encode and decode:

```bash
base64 -d file     # decode
base64 file        # encode
```

The `-d` flag stands for **decode**, reversing the encoding back to the original text.

## Conclusion
After decoding the file, the plain-text password for the next level was revealed.
