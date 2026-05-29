# 02-file-system-and-permissions.md

# Linux File System & Permissions

## Introduction to the Linux File System

Linux stores EVERYTHING in one tree structure.

Starts from:

```bash
/
```

Called:

> root directory.

---

## Linux File System Directories

| Directory | Purpose             |
| --------- | ------------------- |
| `/home`   | user folders        |
| `/bin`    | important commands  |
| `/etc`    | configuration files |
| `/var`    | logs/data           |
| `/tmp`    | temporary files     |
| `/root`   | root user home      |

---

## touch and echo Commands

### touch

Creates empty files.

```bash
touch file.txt
```

---

### echo

Creates text inside files.

```bash
echo "hello" > file.txt
```

---

## cat Command

Displays file contents.

### Example 1

```bash
cat file.txt
```

### Example 2

```bash
cat file1.txt file2.txt
```

---

## head and tail Commands

### head

Shows beginning of file.

```bash
head file.txt
```

---

### tail

Shows end of file.

```bash
tail file.txt
```

---

### Custom Line Amount

```bash
head -3 file.txt
```

```bash
tail -2 file.txt
```

---

## cp Command

Copies files and folders.

### Example 1

```bash
cp file.txt backup.txt
```

### Example 2

```bash
cp -r folder1 folder2
```

`-r` means recursive.

---

## mv and rm Commands

### mv

Moves or renames files.

```bash
mv old.txt new.txt
```

---

### rm

Deletes files.

```bash
rm file.txt
```

Deleted files usually cannot be recovered.

---

## mkdir, rmdir and rm -r

### mkdir

Creates folders.

```bash
mkdir test
```

---

### rmdir

Deletes EMPTY folders.

```bash
rmdir test
```

---

### rm -r

Deletes folders and contents.

```bash
rm -r test
```

---

## Spaces in Folder Names

Linux dislikes spaces.

### Option 1

```bash
cd My\ Folder
```

### Option 2

```bash
cd "My Folder"
```

### Best Practice

```bash
my_folder
```

---

## VIM Text Editor

VIM is a terminal text editor.

Open file:

```bash
vim file.txt
```

---

## Important VIM Modes

| Mode    | Purpose    |
| ------- | ---------- |
| Normal  | navigation |
| Insert  | typing     |
| Command | save/quit  |

---

## VIM Navigation

### Enter Insert Mode

Press:

```bash
i
```

---

### Save and Quit

Press:

```bash
Esc
```

Then:

```bash
:wq
```

---

### Quit Without Saving

```bash
:q!
```

---

## sudo Command

`sudo` means:

> run command as administrator.

Example:

```bash
sudo apt update
```

---

## Root User

Root is the most powerful Linux user.

Root can:

* access everything
* delete everything
* change everything

---

## Dangerous Command

```bash
rm -rf /
```

This can destroy a Linux system.

Never run random commands online.

---

## Users

Show current user:

```bash
whoami
```

Create user:

```bash
sudo adduser john
```

Switch user:

```bash
su john
```

---

## Groups

Groups help manage permissions.

Show groups:

```bash
groups
```

Add user to group:

```bash
sudo usermod -aG sudo john
```

---

## Introduction to File Permissions

Permissions control access.

Linux permissions:

| Symbol | Meaning |
| ------ | ------- |
| r      | read    |
| w      | write   |
| x      | execute |

---

## Permission Example

```bash
-rwxr-xr--
```

---

## Binary, Octal and String Representation

Permissions use numbers.

| Number | Permission |
| ------ | ---------- |
| 4      | read       |
| 2      | write      |
| 1      | execute    |

Add numbers together.

### Example

```bash
7 = rwx
6 = rw-
5 = r-x
```

---

## chmod Calculator

Common permissions:

| Number | Meaning                 |
| ------ | ----------------------- |
| 777    | everyone full access    |
| 755    | owner full access       |
| 644    | normal file permissions |

---

## chmod Command

### Symbolic Mode

```bash
chmod +x script.sh
```

---

### Numeric Mode

```bash
chmod 755 script.sh
```

---

## Grouping Permissions

```bash
chmod u+x file.txt
```

| Symbol | Meaning |
| ------ | ------- |
| u      | user    |
| g      | group   |
| o      | others  |

---

## Changing Ownership

### Change Owner

```bash
sudo chown john file.txt
```

### Change Group

```bash
sudo chgrp developers file.txt
```
