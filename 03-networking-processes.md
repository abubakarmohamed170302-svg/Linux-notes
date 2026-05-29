# Linux Networking & Processes

## Introduction to Standard Streams

Linux has 3 streams.

| Stream | Purpose       |
| ------ | ------------- |
| stdin  | input         |
| stdout | normal output |
| stderr | errors        |

---

## Standard Input, Output and Error

### stdout

```bash
echo "hello"
```

---

### Redirect Output

```bash
echo "hello" > file.txt
```

---

### stderr

Errors are usually displayed separately from normal output.

Example:

```bash
ls fakefolder
```

This produces an error message through `stderr`.

---

## Pipes and Redirection

Pipes send output from one command into another command.

Pipe symbol:

```bash
|
```

Example:

```bash
ls | grep ".txt"
```

This:

1. lists files
2. sends output into `grep`
3. filters `.txt` files

---

## Redirecting Output

### Overwrite File

```bash
echo "hello" > file.txt
```

---

### Append to File

```bash
echo "world" >> file.txt
```

---

## Networking Basics

Linux networking allows systems to communicate with each other.

Common networking tasks include:

* SSH connections
* checking open ports
* troubleshooting servers
* transferring files

---

## SSH

SSH means:

> Secure Shell

Used to securely connect to remote Linux systems.

### Example

```bash
ssh user@server-ip
```

### Example With Port

```bash
ssh user@server-ip -p 2222
```

---

## SCP

SCP means:

> Secure Copy

Used to securely transfer files over SSH.

### Example

```bash
scp file.txt user@server:/home/user/
```

---

## Processes

A process is a running program on Linux.

Examples:

* web servers
* Python scripts
* Bash scripts
* databases

Each process has:

* a Process ID (PID)
* an owner
* memory usage
* CPU usage

---

## ps Command

Shows running processes.

### Example

```bash
ps aux
```

### Breakdown

| Option | Meaning                      |
| ------ | ---------------------------- |
| a      | all users                    |
| u      | detailed output              |
| x      | include background processes |

---

## grep with Processes

`grep` can filter process output.

### Example

```bash
ps aux | grep nginx
```

This searches for running `nginx` processes.

---

## kill Command

Stops running processes.

### Example

```bash
kill 1234
```

Where:

* `1234` = process ID (PID)

---

## Background Processes

Run a process in the background using:

```bash
command &
```

Example:

```bash
python app.py &
```

---

## System Monitoring

Linux includes tools for monitoring systems.

### top

Shows live system usage.

```bash
top
```

Displays:

* CPU usage
* memory usage
* running processes

---

### htop

Improved version of `top`.

Install:

```bash
sudo apt install htop
```

Run:

```bash
htop
```

---

## Netcat (nc)

`nc` means:

> netcat

Used for:

* connecting to ports
* testing services
* network troubleshooting

### Example

```bash
nc localhost 3000
```

---

## OpenSSL

Used for secure SSL/TLS connections.

### Example

```bash
openssl s_client -connect localhost:443
```

---

## lsof

`lsof` means:

> list open files

Used to identify:

* which process is using a file
* open network connections
* active services

### Example

```bash
lsof /var/log/syslog
```

---

## Common Networking Commands

### Ping

Checks network connectivity.

```bash
ping google.com
```

---

### IP Address

Show IP information.

```bash
ip a
```

---

### Check Open Ports

```bash
ss -tulnp
```

---

## Key Concepts Learned

### SSH

Secure remote Linux access.

### PID

Unique process ID.

### Pipes

Send output between commands.

### Streams

Linux input/output channels.

### System Monitoring

Tracking Linux resource usage.

### Networking

Communication between Linux systems.
