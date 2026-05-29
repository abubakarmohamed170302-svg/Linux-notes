# Terminal Basics

## Introduction to the Terminal

The terminal is a text-based way to interact with Linux.

Instead of clicking buttons:

* you type commands
* Linux responds

Think of the terminal like:

> a conversation between YOU and the computer.

Example:

```bash
pwd
```

Linux responds with your current location.

---

## Why Developers Use the Terminal

The terminal is:

* faster
* powerful
* used on servers
* used for automation
* important in DevOps and Cloud

Most professional Linux work happens in the terminal.

---

## The Terminal on Ubuntu

Ubuntu includes a built-in terminal.

Open it using:

```bash
Ctrl + Alt + T
```

You usually see something like:

```bash
abu@ubuntu:~$
```

### Breakdown

| Part     | Meaning       |
| -------- | ------------- |
| `abu`    | username      |
| `ubuntu` | computer name |
| `~`      | home folder   |
| `$`      | normal user   |

---

## Quick Introduction to Commands

Commands tell Linux what to do.

Example:

```bash
ls
```

Meaning:

> list files and folders.

Commands usually follow this structure:

```bash
command option target
```

Example:

```bash
ls -l Documents
```

---

## What are Commands?

Commands are programs.

When you type:

```bash
ls
```

Linux:

1. searches for the `ls` program
2. runs it
3. shows output

Commands live in folders like:

```bash
/bin
/usr/bin
```

---

## The Manual Page

Linux includes built-in manuals.

Use:

```bash
man command
```

Example:

```bash
man ls
```

Meaning:

> show the manual page for `ls`.

---

## Important Manual Navigation

| Key        | Action             |
| ---------- | ------------------ |
| `q`        | quit               |
| `/word`    | search             |
| `n`        | next search result |
| arrow keys | move               |

---

# First Commands

## ls

```bash
ls
```

Shows files and folders.

### Example

```bash
ls -l
```

Shows detailed information.

---

## pwd

```bash
pwd
```

Means:

> print working directory.

Shows your current location.

---

## cd

```bash
cd foldername
```

Means:

> change directory.

### Example

```bash
cd Documents
```

### Move Back One Folder

```bash
cd ..
```

---

## echo

Prints text.

```bash
echo "Hello"
```

---

## grep

Searches for text.

```bash
grep "hello" notes.txt
```

---

## cat

Displays file contents.

```bash
cat notes.txt
```

---

## Creating Files

Using `touch`:

```bash
touch notes.txt
```

Using `echo`:

```bash
echo "hello" > notes.txt
```

---

## Shell, Programs and Binaries

### Shell

The shell listens to your commands.

### Program

A program performs tasks.

### Binary

A binary is an executable file.

Example:

```bash
/bin/ls
```

---

## Programs and Binaries

Programs are stored in folders like:

```bash
/bin
/usr/bin
```

Find command location:

```bash
which ls
```

Example output:

```bash
/bin/ls
```

---

## Introduction to the Shell

The shell acts as a middleman.

```text
You → Shell → Linux
```

You type commands.
The shell interprets them.
Linux executes them.

---

## Other Shells

Different shells exist.

| Shell | Description             |
| ----- | ----------------------- |
| Bash  | default Linux shell     |
| ZSH   | advanced shell          |
| Fish  | beginner-friendly shell |
| SH    | original shell          |

---

## Installing ZSH

Install ZSH:

```bash
sudo apt install zsh
```

Check version:

```bash
zsh --version
```

---

## Setting ZSH as Default

```bash
chsh -s $(which zsh)
```

Restart the terminal afterwards.

---

## Debugging Shell Problems

Check current shell:

```bash
echo $SHELL
```

If ZSH is not loading:

* restart terminal
* log out and back in
* check installation
