# Security Tools Familiarization

This document covers the four tools named in the ApexPlanet Task 1 brief. Use them only on your own lab systems or systems for which you have explicit authorization.

## 1. Wireshark — packet capture

**Purpose:** Capture and inspect network packets.

Suggested lab exercise:
1. Open Wireshark in Kali and select the interface connected to your private lab network.
2. Start a capture.
3. In another terminal, ping your own Metasploitable2 VM.
4. Stop the capture.
5. Apply the display filter `icmp`.
6. Inspect source/destination addresses and ICMP request/reply packets.
7. Save a sanitized capture as `Lab-Setup/wireshark-capture/wireshark-icmp.pcapng`.

Do not capture unrelated traffic or publish captures containing credentials, tokens or personal data.



## 2. Nmap — service discovery

**Purpose:** Identify reachable ports and, when requested, attempt to identify services and versions.

Run only against your lab target:

```bash
nmap -sV <TARGET_IP>
```

Replace `<TARGET_IP>` with the actual Metasploitable2 IP. Save the output only after checking it for sensitive information. Explain that open ports indicate reachable services, not automatically exploitable vulnerabilities.



## 3. Burp Suite — web proxy

**Purpose:** Inspect HTTP requests and responses from an application you are authorized to test.

Suggested familiarization:
1. Open Burp Suite.
2. Use its built-in browser or configure a browser proxy as instructed by the installed version.
3. Visit a local test application, if available.
4. Inspect a request and response in the HTTP history.
5. Record what the method, path, status code and headers mean.

Do not intercept or modify traffic belonging to other people or services without permission.


## 4. Netcat — network debugging

**Purpose:** Test simple TCP/UDP connectivity and exchange data in controlled lab scenarios.

On one Kali terminal:

```bash
nc -lv 4444
```

On another terminal on the same Kali VM:

```bash
nc 127.0.0.1 4444
```

Type a harmless message in the client terminal and verify that it appears in the listener terminal. Stop the listener with `Ctrl+C` when finished. If your Netcat version uses different flags, consult `nc -h` or its manual.



