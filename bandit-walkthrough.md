# bandit-walkthrough.md

# OverTheWire Bandit Walkthrough 🐧

## What is Bandit?

Bandit is a Linux wargame from OverTheWire designed to teach:

* Linux commands
* file navigation
* permissions
* networking
* SSH
* scripting basics
* problem-solving

Website:

```text
https://overthewire.org/wargames/bandit/
```

---

# Connecting to Bandit

```bash id="f77gh0"
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

### What it means

| Part                          | Meaning                  |
| ----------------------------- | ------------------------ |
| `ssh`                         | secure remote connection |
| `bandit0`                     | username                 |
| `bandit.labs.overthewire.org` | server                   |
| `-p 2220`                     | custom SSH port          |

---

# Commands Frequently Used

| Command   | Purpose               |
| --------- | --------------------- |
| `ls`      | list files            |
| `cd`      | change directory      |
| `cat`     | display file contents |
| `find`    | search for files      |
| `grep`    | search text           |
| `sort`    | sort lines            |
| `uniq`    | filter duplicates     |
| `strings` | extract readable text |
| `file`    | identify file type    |
| `ssh`     | remote login          |
| `scp`     | copy files securely   |
| `chmod`   | change permissions    |
| `diff`    | compare files         |

---

# Bandit Level 0 → 1

```bash id="6ubt6x"
ls
cat readme
```

### Key Lesson

* `ls` lists files
* `cat` displays file contents
* passwords are stored inside files

---

# Bandit Level 1 → 2

```bash id="jhlb3s"
cat ./-
```

### Key Lesson

Files named `-` require `./` so Linux treats them as filenames.

---

# Bandit Level 2 → 3

```bash id="e7y9m8"
cat ./"--spaces in this filename--"
```

### Key Lesson

Quotes handle spaces safely in filenames.

---

# Bandit Level 3 → 4

```bash id="mjlwm0"
ls -a
```

### Key Lesson

`-a` shows hidden files beginning with `.`

---

# Bandit Level 4 → 5

```bash id="q28jsl"
file ./*
```

### Key Lesson

Use `file` to identify readable files and file types.

---

# Bandit Level 5 → 6

```bash id="5v0bd0"
find . -type f -size 1033c -readable
```

### Key Lesson

`find` searches files using conditions like:

* size
* permissions
* type

---

# Bandit Level 6 → 7

```bash id="zkp2g0"
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### Key Lesson

* search entire filesystem
* filter by owner/group
* suppress errors using:

```bash id="w2xq3g"
2>/dev/null
```

---

# Bandit Level 8 → 9

```bash id="x8nlf1"
sort data.txt | uniq -u
```

### Key Lesson

Pipes combine commands together.

---

# Bandit Level 9 → 10

```bash id="l8g62o"
strings data.txt | grep "="
```

### Key Lesson

* `strings` extracts readable text
* `grep` filters matching lines

---

# Bandit Level 10 → 11

```bash id="o4t4nh"
base64 -d data.txt
```

### Key Lesson

Decode Base64 encoded data.

---

# Bandit Level 11 → 12

```bash id="9u9z3y"
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### Key Lesson

ROT13 shifts letters 13 positions in the alphabet.

---

# Bandit Level 12 → 13

### Important Commands

```bash id="mjlwm1"
xxd -r
gzip -d
bzip2 -d
tar -xf
file
```

### Key Lesson

Always use:

```bash id="myjlwm"
file filename
```

to identify file types before extracting them.

---

# Bandit Level 13 → 14

### Important Commands

```bash id="iq0o9p"
scp
chmod 600
ssh -i
```

### Key Lesson

SSH can use private key authentication instead of passwords.

---

# Bandit Level 14 → 15

```bash id="pcwrrf"
cat password | nc localhost 30000
```

### Key Lesson

`nc` (netcat) is used for port communication.

---

# Bandit Level 15 → 16

```bash id="30bncx"
openssl s_client -connect localhost:30001
```

### Key Lesson

Some services require encrypted SSL/TLS communication.

---

# Bandit Level 16 → 17

### Important Commands

```bash id="lmfjlwm"
nmap -sV
openssl s_client
scp
ssh -i
```

### Key Lesson

This level combined:

* networking
* SSL
* SSH
* port scanning
* file permissions

---

# Bandit Level 17 → 18

```bash id="p1jlwm"
diff passwords.old passwords.new
```

### Key Lesson

`diff` compares changes between files.

---

# Key Linux Skills Learned

* Linux navigation
* SSH
* file permissions
* networking
* process investigation
* pipelines
* text processing
* compression formats
* remote access
* troubleshooting

---

# Why Bandit is Useful

Bandit helps build:

* Linux confidence
* terminal problem-solving
* command-line thinking
* troubleshooting skills

These are essential skills for:

* DevOps
* Cloud Engineering
* Linux Administration
* Cybersecurity
