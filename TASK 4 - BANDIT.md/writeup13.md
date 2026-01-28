# Writeup 13

## Challenge Name
MULTI-LAYER COMPRESSION AND ENCODING

---

## Objective
The objective of this level is to extract the password hidden inside a file that has gone through **multiple layers of encoding and compression**. This requires identifying each file type correctly and applying the appropriate decoding or decompression technique step by step.

---

## Creating a Temporary Working Directory
Since write access to the home directory is restricted, a temporary directory was created in `/tmp` to safely work with files.

### Commands Used
```bash
cd /tmp
mktemp -d
cd /tmp/tmp.RNlhJrqT2r
```

---

## Copying and Preparing the File
The original `data.txt` file was copied into the temporary directory and renamed for clarity.

### Commands Used
```bash
cp ~/data.txt .
mv data.txt hexdump_data
```

---

## Analyzing the File
The file contents were examined to understand its structure.

### Command Used
```bash
cat hexdump_data | head
```

### Observation
The file appeared to be a **hex dump**, indicating that it needed to be converted back into binary format.

---

## Reversing the Hex Dump
The hex dump was converted back into a binary file using `xxd`.

### Command Used
```bash
xxd -r hexdump_data compressed_data
```

---

## Decompressing the File (Gzip)
The binary file was identified as gzip-compressed and decompressed accordingly.

### Commands Used
```bash
mv compressed_data compressed_data.gz
gzip -d compressed_data.gz
```

---

## Decompressing the File (Bzip2)
The resulting file was then identified as bzip2-compressed.

### Commands Used
```bash
mv compressed_data compressed_data.bz2
bzip2 -d compressed_data.bz2
```

---

## Extracting Tar Archive
After decompression, the file was found to be a tar archive and extracted.

### Commands Used
```bash
mv compressed_data compressed_data.tar
tar -xf compressed_data.tar
```

---

## Handling Nested Archives
Further extracted files revealed additional compressed files which were decoded step by step.

### Commands Used
```bash
tar -xf data5.bin
bzip2 -d data6.bin
tar -xf data6.bin.out
```

---

## Final Decompression
The final file was identified as gzip-compressed and decompressed.

### Commands Used
```bash
mv data8.bin data8.gz
gzip -d data8.gz
```

---

## Extracting the Password
The contents of the final decoded file were displayed.

### Command Used
```bash
cat data8
```

### Output
```text
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

---

## Identifying the Password
The password obtained from the decoded output is:

```text
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

---

## Conclusion
The password for the next Bandit level was successfully retrieved by:
- Working in a temporary directory
- Identifying file formats using hex analysis
- Sequentially decoding gzip, bzip2, and tar layers

This password can now be used to log in to **Bandit Level 13**.
