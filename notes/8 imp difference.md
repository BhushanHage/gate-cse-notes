---
title: "Important Differences Cheat Sheet"
output: html_document
---

# Important Differences Cheat Sheet

## 1. OSI Model vs TCP/IP Model

| Feature | OSI Model | TCP/IP Model |
|---|---|---|
| Layers | 7 | 4 or 5 |
| Nature | Reference model | Practical model |
| Usage | Conceptual learning | Real-world internet |
| Layer split | More detailed | Less detailed |

---

## 2. TCP vs UDP

| Feature | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Ordering | Ordered delivery | No ordering guarantee |
| Speed | Slower | Faster |
| Overhead | Higher | Lower |
| Example use | Web, email, file transfer | Streaming, DNS, gaming |

---

## 3. Switch vs Router

| Feature | Switch | Router |
|---|---|---|
| OSI layer | Data Link | Network |
| Address used | MAC | IP |
| Unit forwarded | Frame | Packet |
| Function | Connects devices in LAN | Connects networks |

---

## 4. Hub vs Switch

| Feature | Hub | Switch |
|---|---|---|
| Layer | Physical | Data Link |
| Forwarding | Broadcast to all ports | Sends to selected port |
| Intelligence | None | Uses MAC table |
| Efficiency | Low | High |

---

## 5. MAC vs IP

| Feature | MAC Address | IP Address |
|---|---|---|
| Layer | Data Link | Network |
| Type | Physical address | Logical address |
| Scope | Local LAN | Across networks |
| Format | Hexadecimal | IPv4/IPv6 format |
| Change | Usually fixed | Can change |

---

## 6. Frame vs Packet vs Segment

| Unit | Layer | Meaning |
|---|---|---|
| Segment | Transport | Data unit of transport layer |
| Packet | Network | Data unit of network layer |
| Frame | Data Link | Data unit of data link layer |
| Bits | Physical | Raw transmission bits |

---

## 7. Distance Vector vs Link State

| Feature | Distance Vector | Link State |
|---|---|---|
| Information shared | Routing table | Full topology |
| Convergence | Slower | Faster |
| Example | RIP | OSPF |
| Loop chance | Higher | Lower |

---

## 8. IPv4 vs IPv6

| Feature | IPv4 | IPv6 |
|---|---|---|
| Address length | 32 bits | 128 bits |
| Address space | Limited | Very large |
| Notation | Decimal dotted | Hexadecimal |
| NAT need | Common | Less required |

---

## 9. ARP vs ICMP

| Feature | ARP | ICMP |
|---|---|---|
| Purpose | IP to MAC mapping | Error reporting and diagnostics |
| Layer relation | Between network and data link | Network layer support |
| Example use | Local frame delivery | Ping, unreachable messages |

---

## 10. HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|---|---|---|
| Security | No encryption | Encrypted |
| Port | 80 | 443 |
| Use | Normal web communication | Secure web communication |

---

## 11. SMTP vs POP3 vs IMAP

| Protocol | Purpose |
|---|---|
| SMTP | Send email |
| POP3 | Retrieve email |
| IMAP | Access and manage email on server |

---

## 12. Telnet vs SSH

| Feature | Telnet | SSH |
|---|---|---|
| Security | Insecure | Secure |
| Data transfer | Plain text | Encrypted |

---

## 13. DNS vs DHCP

| Feature | DNS | DHCP |
|---|---|---|
| Purpose | Name to IP resolution | Automatic IP configuration |

---

## 14. Router vs Gateway

| Feature | Router | Gateway |
|---|---|---|
| Function | Connects networks | Protocol conversion |
| Layer | Network | Higher layers |

---

## 15. Client-Server vs Peer-to-Peer

| Feature | Client-Server | Peer-to-Peer |
|---|---|---|
| Structure | Centralized | Decentralized |
| Control | Server-based | Shared among peers |
| Example | Web, email | File sharing |

---

## 16. Common Port Numbers

| Protocol | Port |
|---|---|
| HTTP | 80 |
| HTTPS | 443 |
| FTP | 21 |
| SMTP | 25 |
| POP3 | 110 |
| IMAP | 143 |
| DNS | 53 |
| Telnet | 23 |
| SSH | 22 |
| DHCP | 67/68 |
| SNMP | 161 |

---

## 17. Quick Memory Points

- TCP is reliable, UDP is fast.
- Router works at network layer.
- Switch works at data link layer.
- Hub works at physical layer.
- MAC is local, IP is logical.
- Port identifies application.
- IP identifies host.
- Frame, packet, and segment belong to different layers.

---

## 18. Final Revision List

### Must remember
- OSI vs TCP/IP
- TCP vs UDP
- Switch vs Router
- Hub vs Switch
- MAC vs IP
- Frame vs Packet vs Segment
- IPv4 vs IPv6
- Distance Vector vs Link State
- ARP vs ICMP
- HTTP vs HTTPS
- SMTP vs POP3 vs IMAP
- Telnet vs SSH
- DNS vs DHCP
