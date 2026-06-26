# Bandit Level 12 → 13

## Objective
`data.txt` is a hexdump of a file that has been compressed multiple times. We need to reverse the hexdump and repeatedly decompress the file until we reach the plain-text password.

## Solution
Create a working directory in `/tmp`, copy the file there, reverse the hexdump with `xxd -r`, then iteratively identify each compression format and decompress accordingly until the file type is ASCII text.

## Commands Used
```bash
mkdir /tmp/bandit12_work
cp data.txt /tmp/bandit12_work
cd /tmp/bandit12_work
xxd -r data.txt > data.bin
file data.bin
```

Then, repeat the identify-rename-decompress cycle:
```bash
# gzip layer
mv data.bin data.gz
gunzip data.gz

# bzip2 layer
file data
mv data data.bz2
bzip2 -d data.bz2

# tar layer
file data
mv data data.tar
tar -xf data.tar

# ... repeat until:
file data.bin    # → ASCII text
```

## What I Learned

### mkdir
Creates a new directory:
```bash
mkdir /tmp/my_folder
```

### xxd and the -r Flag
`xxd` creates or reads hexdumps. The `-r` (reverse) flag converts a hexdump back into the original binary file:
```bash
xxd -r hexdump.txt > output.bin
```

### mv
Renames or moves files:
```bash
mv oldname newname
```

### Decompression Commands

| Command | Format | Usage |
|---------|--------|-------|
| `gunzip file.gz` | gzip | Extracts `.gz` files |
| `bzip2 -d file.bz2` | bzip2 | Extracts `.bz2` files (`-d` = decompress) |
| `tar -xf file.tar` | tar | Extracts `.tar` archives (`-x` = extract, `-f` = file) |

### Key Strategy
After each decompression step, always run `file <output>` to identify the new file type before deciding the next step.

## Conclusion
After multiple rounds of decompression, we finally reached an ASCII text file containing the password for the next level.
