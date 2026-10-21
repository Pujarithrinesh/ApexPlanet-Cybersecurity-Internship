# Wireshark Capture Evidence

Store a small, sanitized packet capture generated during your own Task 1 lab exercise in this folder.

Suggested filename:
- `wireshark-icmp.pcapng`

Suggested procedure:
1. Open Wireshark on the interface connected to your private lab.
2. Start capturing.
3. Ping your own Metasploitable2 target from Kali.
4. Stop capturing and apply the display filter `icmp`.
5. Confirm the capture contains only appropriate lab traffic.
6. Save the capture and note the test details below.

## Capture record

- Date/time: `2026-10-19, 16:21 PM IST`
- Capture interface: `eth0`
- Source VM/IP: `Kali Linux / 172.17.54.136`
- Destination VM/IP: `Metasploitable2 / 172.17.54.233`
- Display filter used: `icmp`
- Observed packets: `4 ICMP Echo Requests and 4 ICMP Echo Replies`
- File name: `wireshark-icmp.pcapng`

Do not commit captures that contain credentials, cookies, tokens, private communications or other sensitive information. If you cannot safely sanitize a capture, keep it out of the public repository and include a screenshot of the filtered lab traffic instead.
