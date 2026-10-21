# Lab Setup Report — Task 1

**Internship:** ApexPlanet Cybersecurity & Ethical Hacking Internship  
**Task:** Foundation & Environment Setup  
**Student:** `Pujari Thrinesh`  
**Date:** `20/10/2026`

## 1. Objective

The objective is to establish an isolated cybersecurity lab, practise foundational Linux and networking commands, understand basic cryptography, and familiarize myself with Wireshark, Nmap, Burp Suite and Netcat.

## 2. Environment

| Component | Details |
|---|---|
| Host operating system | Windows 11 |
| Virtualization software | VirtualBox |
| Testing VM | Kali Linux |
| Target VM | Metasploitable2 |
| Network mode | 
| Kali IP/prefix |
| Target IP|

Do not guess IP addresses or software versions. Fill this table from the running systems.

## 3. Lab network configuration

Describe how the two virtual machines are attached to the same private/Host-Only lab network. Explain how this limits exposure compared with putting a deliberately vulnerable VM directly on a public or bridged network.

**Evidence:**  
- VirtualBox overview: `screenshots/virtualbox-vms.png`
- Network configuration: `screenshots/lab-network-settings.png`

Replace the example filenames above with the filenames you actually save.

## 4. Connectivity test

Command used:

```bash
ping -c 4 <TARGET_IP>
```

Target IP: `172.17..54.233`  
Actual result: `5 packets transmitted, 5 received, 0% packet loss, time 4010ms`  
Interpretation: PING 172.17.54.233 (172.17.54.233) 56(84) bytes of data.
64 bytes from 172.17.54.233: icmp_seq=1 ttl=64 time=20.9 ms
64 bytes from 172.17.54.233: icmp_seq=2 ttl=64 time=9.48 ms
64 bytes from 172.17.54.233: icmp_seq=3 ttl=64 time=8.11 ms
64 bytes from 172.17.54.233: icmp_seq=4 ttl=64 time=20.0 ms
64 bytes from 172.17.54.233: icmp_seq=5 ttl=64 time=0.588 ms

--- 172.17.54.233 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4010ms
rtt min/avg/max/mdev = 0.588/11.814/20.885/7.674 ms


**Evidence:** `screenshots/kali-to-target-ping.png`

## 5. Linux fundamentals

Summarize the commands practised, including navigation (`pwd`, `ls`, `cd`), file creation, permissions (`chmod`), package management (`apt`, `dpkg`) and networking (`ip addr`, `ip route`, `ping`, `ss` or other tools actually used).

| Command | Purpose | Result/evidence |
|---|---|---|
| `pwd`, `ls -la` | Directory navigation and listing |
| `chmod 600 permission-demo.txt` | Demonstrate file permissions | 
| `ip addr`, `ip route` | Inspect interfaces and routes | 
| `ping -c 4 <TARGET_IP>` | Test lab reachability | 

## 6. Networking concepts

Summarize the OSI layers, TCP/IP, DNS, HTTP versus HTTPS, IP addressing, subnetting and NAT. Distinguish concepts studied from commands actually tested.

## 7. Cryptography practical

Document the OpenSSL encryption/decryption demonstration, MD5/SHA-256 hash comparison and TLS certificate inspection if performed.

- Encryption result: Successfully encrypted the test message
using OpenSSL AES-256-CBC with PBKDF2-based password derivation.

- Decryption/plaintext comparison: Successfully decrypted the
encrypted file using the same password. The recovered plaintext
matched the original message.

- Hashing result: "Successfully calculated MD5 and SHA-256 hashesfor the test file. Both commands produced hexadecimal digests.
The SHA-256 hashes of the original and identical copied files matched, confirming that their contents were identical at the time of testing."

- TLS inspection result: Successfully connected to the test website using OpenSSL and inspected the TLS certificate
information, including the subject, issuer and validity dates. The verification result was recorded from the actual command
output.

Never include the encryption password or private keys in this report.

## 8. Tool familiarization

### Wireshark
Capture interface: `eth0`  
Filter: `icmp`  
Observed packets: `4 ICMP Echo Requests and 4 ICMP Echo Replies`  
Capture file: `wireshark-capture/wireshark-icmp.pcapng`

### Nmap
Command: `nmap -sV 172.17.54.233`  
Target: `172.17.54.233`  
Actual summary: 
Starting Nmap 7.94SVN ( https://nmap.org ) at 2026-10-19 17:24 IST
Nmap scan report for 172.17.54.233
Host is up (0.0069s latency).
Not shown: 977 closed tcp ports (conn-refused)
PORT     STATE SERVICE     VERSION
21/tcp   open  ftp         vsftpd 2.3.4
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
23/tcp   open  telnet      Linux telnetd
25/tcp   open  smtp        Postfix smtpd
53/tcp   open  domain      ISC BIND 9.4.2
80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
111/tcp  open  rpcbind     2 (RPC #100000)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
512/tcp  open  exec        netkit-rsh rexecd
513/tcp  open  login
514/tcp  open  tcpwrapped
1099/tcp open  java-rmi    GNU Classpath grmiregistry
1524/tcp open  bindshell   Metasploitable root shell
2049/tcp open  nfs         2-4 (RPC #100003)
2121/tcp open  ftp         ProFTPD 1.3.1
3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
5900/tcp open  vnc         VNC (protocol 3.3)
6000/tcp open  X11         (access denied)
6667/tcp open  irc         UnrealIRCd
8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)
8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 12.78 seconds

### Burp Suite
Local application: Python HTTP server running on http://127.0.0.1:8000  
Request/response inspected: Inspected the HTTP request and response in Burp Suite's Proxy HTTP history. Recorded the actual request method, path, response status code, and relevant headers.

### Netcat
Test performed: Started a TCP listener on port 4444 using Netcat v1.10-48.2 and connected to it from a second Kali
Linux terminal using `nc -v 127.0.0.1 4444`.

Observed result: Sent the message "ApexPlanet Task 1 Netcat Test" from the client terminal and verified that it appeared
in the listener terminal. This demonstrated successful local TCP communication.

## 9. Results, limitations and troubleshooting

List what worked, what did not, and what remains incomplete. Include actual error messages where useful, after removing secrets or sensitive details.

## 10. Conclusion

Summarize what the lab demonstrates and identify next learning steps. Do not state that all requirements are complete until each item has been tested or documented appropriately.

## Appendix — screenshots

Insert screenshots into this report or reference the files in the `screenshots/` directory. Use a short caption for each image and ensure text is readable.
