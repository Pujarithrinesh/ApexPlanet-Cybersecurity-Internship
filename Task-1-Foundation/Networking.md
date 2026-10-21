# Networking Fundamentals

## 1. OSI model

| Layer | Name | Main idea | Examples |
|---:|---|---|---|
| 7 | Application | Network services used by applications | HTTP, DNS |
| 6 | Presentation | Data representation, encoding and related transformations | Data formats, encryption concepts |
| 5 | Session | Establishing and managing communication sessions | Session-management concepts |
| 4 | Transport | End-to-end transport and ports | TCP, UDP |
| 3 | Network | Logical addressing and routing | IP |
| 2 | Data Link | Local-link frames and hardware addressing | Ethernet, MAC addresses |
| 1 | Physical | Transmission of bits over a medium | Copper, fibre, radio |

The OSI model is a learning model. Real protocol stacks do not always map perfectly to one OSI layer.

## 2. TCP/IP model

A common four-layer view:
1. **Application:** HTTP, DNS and other application protocols.
2. **Transport:** TCP and UDP.
3. **Internet:** IP addressing and routing.
4. **Link:** Local network access, such as Ethernet or Wi-Fi.

## 3. DNS, HTTP and HTTPS

- **DNS** resolves names to records, including IP addresses.
- **HTTP** is an application protocol for web communication.
- **HTTPS** is HTTP protected by TLS, providing encryption in transit and helping authenticate the server through certificates.

Useful commands:

```bash
getent hosts example.com
curl -I https://example.com
```

These examples require working DNS and Internet connectivity. If offline, record that the tests could not be completed.

## 4. IP addressing, subnetting and NAT

- An **IP address** identifies a network interface logically.
- A **private IPv4 address** is intended for internal networks and is not globally routed on the public Internet.
- A **public IP address** is globally routable, subject to routing and filtering.
- **Subnetting** divides an address block into smaller networks using a prefix length, such as `/24`.
- **NAT** translates network addresses. A common use is allowing several private IPv4 devices to share one public IPv4 address.

Common private IPv4 ranges:
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

## 5. Lab connectivity checks

Run these in Kali and replace the placeholder with your own target's address:

```bash
ip addr
ip route
ping -c 4 <TARGET_IP>
```

Record:
- Kali IP/prefix: `172.17.54.136`
- Target IP: `72.17.54.233`
- Network mode: `Bridged Adapter`
- Ping result: --- 172.17.54.233 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4006ms
rtt min/avg/max/mdev = 0.859/11.952/25.598/9.843 ms


Do not publish an address if it reveals sensitive information about a real organization or network.

## 6. Networking evidence

| Test | Expected observation | Actual result |
|---|---|---|
| `ip addr` | Interface addresses and state | 
| `ip route` | Local routes and default route, if configured | 
| `ping -c 4 <TARGET_IP>` | Replies if reachable and ICMP is permitted | 
| `getent hosts example.com` | DNS result if name resolution works |
| `curl -I https://example.com` | HTTP response headers if connection succeeds | 

## 7. Learning check

- [ ] Explain the role of each OSI layer.
- [ ] Compare TCP and UDP.
- [ ] Explain DNS resolution.
- [ ] Explain HTTP versus HTTPS.
- [ ] Identify the lab network prefix and explain whether NAT is involved.
