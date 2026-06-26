# Bandit Level 11 → 12

## Objective
The password is stored in `data.txt`, where all letters have been rotated by 13 positions (ROT13 / Caesar cipher).

## Solution
Use the `tr` command to map each letter to its ROT13 equivalent, effectively decoding the text.

## Commands Used
```bash
ls
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

## What I Learned

### ROT13 (Caesar Cipher with 13 shifts)
ROT13 is a simple substitution cipher where each letter is replaced by the letter 13 positions after it in the alphabet. Since the English alphabet has 26 letters, applying ROT13 twice returns the original text — encoding and decoding use the same operation.

### tr Command
`tr` (translate) maps characters from one set to another:
```bash
tr 'source_set' 'destination_set'
```

### Decoding ROT13 with tr
The mapping `'A-Za-z' 'N-ZA-Mn-za-m'` works as follows:
- `A-Z` → `N-ZA-M`: shifts uppercase letters by 13
- `a-z` → `n-za-m`: shifts lowercase letters by 13

Reading the destination set: start at N, go to Z, wrap back to A, end at M — a 13-position rotation.

## Conclusion
After applying the ROT13 decoding, the password for the next level was revealed.
