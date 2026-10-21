# Linux Cheat Sheet

Commands below are examples for a Kali Linux lab. Some commands may not be installed by default. Run commands only in environments you administer.

## 1. Navigation and files

| Command | Purpose | Example |
|---|---|---|
| `pwd` | Print current directory | `pwd` |
| `ls -la` | List files, including hidden files | `ls -la` |
| `cd` | Change directory | `cd ~/Documents` |
| `mkdir -p` | Create directories | `mkdir -p ~/apexplanet-task1` |
| `touch` | Create an empty file or update timestamp | `touch notes.txt` |
| `cat` | Print file content | `cat notes.txt` |
| `cp` | Copy files | `cp notes.txt notes-backup.txt` |
| `mv` | Move or rename files | `mv notes.txt notes-old.txt` |
| `grep` | Search text | `grep -n 'TODO' README.md` |

## 2. Create a practice directory

```bash
mkdir -p ~/apexplanet-task1
cd ~/apexplanet-task1
printf 'ApexPlanet Task 1 practice\n' > notes.txt
cat notes.txt
pwd
ls -la
```

## 3. Permissions and ownership

- `ls -l file` shows permissions and ownership.
- `chmod` changes permissions.
- `chown` changes ownership and normally requires elevated privileges.

Safe demonstration:

```bash
touch permission-demo.txt
ls -l permission-demo.txt
chmod 600 permission-demo.txt
ls -l permission-demo.txt
```

`chmod 600` gives the owner read/write permission and removes permissions for group and others. Do not change ownership or permissions of system files unnecessarily.

## 4. Package management

```bash
apt --version
dpkg --version
sudo apt update
```

- `apt` provides higher-level package management and dependency handling.
- `dpkg` manages Debian package files and installed-package records.
- `sudo apt update` refreshes package metadata; it does not by itself upgrade installed packages.

Install only packages you need and understand before running package-management commands.

## 5. Processes and system information

```bash
id
uname -a
ps aux
df -h
free -h
```

These show user/group identity, kernel/system information, processes, disk usage and memory usage.

## 6. Networking

```bash
ip addr
ip route
ping -c 4 <TARGET_IP>
ss -tuln
traceroute 127.0.0.1
```

Replace `<TARGET_IP>` with the actual IP of your own lab target. `ss -tuln` lists listening TCP/UDP sockets. Traceroute output can be limited by local configuration or network filtering.

The internship brief also lists `ifconfig` and `netstat`. Modern alternatives are usually `ip addr`/`ip route` and `ss`; older commands may require the `net-tools` package.

## 7. Evidence log

Record actual command output or screenshots:
- Date:
- Command:
- Purpose:
- Result:
- Screenshot filename:
- Any error or limitation:

Do not paste secrets, tokens, passwords or sensitive host information into a public repository.
