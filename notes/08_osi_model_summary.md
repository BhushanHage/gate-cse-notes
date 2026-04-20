# OSI Model Summary

## 1. Introduction

The OSI (Open Systems Interconnection) model is a conceptual framework used to understand how data moves across a network. It divides network communication into seven layers.

### Why it is important
The OSI model helps in:
- understanding networking concepts
- designing network protocols
- troubleshooting communication problems
- answering exam questions in a structured way

---

## 2. The Seven Layers of OSI

From top to bottom:

1. Application
2. Presentation
3. Session
4. Transport
5. Network
6. Data Link
7. Physical

### Easy mnemonic
- All People Seem To Need Data Processing

---

## 3. Layer-wise Responsibilities

### 7. Application Layer
Provides network services to user applications.

### 6. Presentation Layer
Handles data representation, translation, encryption, and compression.

### 5. Session Layer
Manages sessions, dialog control, and synchronization.

### 4. Transport Layer
Provides process-to-process communication.

### 3. Network Layer
Provides logical addressing and routing.

### 2. Data Link Layer
Provides framing, MAC addressing, and error detection.

### 1. Physical Layer
Transmits raw bits through the communication medium.

---

## 4. Protocol Data Units (PDU)

Each layer works with a different data unit.

| Layer | PDU |
|---|---|
| Application | Data |
| Presentation | Data |
| Session | Data |
| Transport | Segment |
| Network | Packet / Datagram |
| Data Link | Frame |
| Physical | Bits |

### GATE point
PDU names are often asked in exams.

---

## 5. Addressing in OSI Layers

| Layer | Address Type |
|---|---|
| Transport | Port number |
| Network | IP address |
| Data Link | MAC address |
| Physical | None |

### Important
- Port numbers identify applications
- IP addresses identify hosts logically
- MAC addresses identify interfaces locally

---

## 6. Encapsulation

### What is encapsulation?
Encapsulation is the process of adding headers and trailers as data moves down the OSI layers.

### How it works
- Application creates data
- Transport adds transport header
- Network adds IP header
- Data Link adds frame header and trailer
- Physical converts into bits and sends

### GATE point
Encapsulation is a very important concept.

---

## 7. Decapsulation

### What is decapsulation?
Decapsulation is the reverse process. The receiver removes headers and trailers while data moves up the layers.

### How it works
- Physical receives bits
- Data Link checks frame and removes its header/trailer
- Network processes packet
- Transport processes segment
- Application receives data

---

## 8. OSI Layer Comparison Table

| Layer | Main Function | Data Unit | Addressing | Example Protocols |
|---|---|---|---|---|
| Application | User services | Data | None | HTTP, FTP, SMTP, DNS |
| Presentation | Translation, encryption | Data | None | SSL/TLS, JPEG, MPEG |
| Session | Session control | Data | None | NetBIOS, RPC |
| Transport | End-to-end delivery | Segment | Port | TCP, UDP |
| Network | Routing | Packet | IP | IP, ICMP, ARP |
| Data Link | Framing, MAC | Frame | MAC | Ethernet, PPP |
| Physical | Bit transmission | Bits | None | Cables, hubs, repeaters |

### Note
ARP is sometimes discussed near the network/data link boundary.

---

## 9. OSI vs TCP/IP Model

### OSI model
- theoretical reference model
- has 7 layers

### TCP/IP model
- practical internet model
- usually shown with 4 or 5 layers

### TCP/IP layers
1. Application
2. Transport
3. Internet
4. Network Access / Link

### Mapping
| OSI Layer | TCP/IP Layer |
|---|---|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

### GATE point
Know the mapping between OSI and TCP/IP models.

---

## 10. Commonly Confused Terms

### Frame vs Packet vs Segment
- Frame → Data Link
- Packet → Network
- Segment → Transport

### Routing vs Forwarding
- Routing chooses the path
- Forwarding sends the packet to next hop

### MAC vs IP
- MAC is local physical address
- IP is logical network address

### TCP vs UDP
- TCP is reliable and connection-oriented
- UDP is connectionless and faster

### Hub vs Switch vs Router
- Hub → Physical
- Switch → Data Link
- Router → Network

---

## 11. Layer Devices

| Device | Layer |
|---|---|
| Repeater | Physical |
| Hub | Physical |
| Switch | Data Link |
| Bridge | Data Link |
| Router | Network |
| Gateway | Higher layers / protocol conversion |

### GATE point
Device-layer association is a frequent exam topic.

---

## 12. Important Networking Services by Layer

### Application layer services
- web
- email
- DNS
- FTP
- DHCP
- SNMP

### Transport layer services
- TCP
- UDP
- ports
- sockets

### Network layer services
- routing
- IP addressing
- ICMP
- ARP

### Data link layer services
- framing
- MAC
- error detection
- flow control
- medium access control

### Physical layer services
- bit transmission
- signal encoding
- media transmission

---

## 13. Quick Memory Tricks

### OSI layers from top to bottom
All People Seem To Need Data Processing

### PDU order
Data → Segment → Packet → Frame → Bits

### Address order
Port → IP → MAC

### Device order
Router > Switch > Hub

---

## 14. Common GATE Questions

You should be able to answer:
- What are the seven OSI layers?
- What is the PDU of each layer?
- What is encapsulation?
- What is decapsulation?
- How does OSI map to TCP/IP?
- Which layer uses port numbers?
- Which layer uses IP addresses?
- Which layer uses MAC addresses?
- Which device belongs to which layer?
- What is the difference between frame, packet, and segment?

---

## 15. High-Yield Revision Table

| Topic | Key Point |
|---|---|
| Application | User services |
| Presentation | Translation, encryption, compression |
| Session | Dialog control |
| Transport | Ports, segments, TCP/UDP |
| Network | IP, routing, packets |
| Data Link | Frames, MAC, CRC |
| Physical | Bits, signals, media |

---

## 16. Final GATE Revision Notes

- OSI has 7 layers.
- Transport layer works with ports and segments.
- Network layer works with IP and packets.
- Data link layer works with MAC and frames.
- Physical layer works with bits and signals.
- Encapsulation adds headers as data moves down the stack.
- Decapsulation removes them at the receiver.
- TCP/IP is the practical model used in real networks.

---

## 17. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach

---

## 18. Final GATE Tip

The OSI model is not just for memorization.  
Questions often test:
- layer function
- layer-specific address
- layer-specific data unit
- device-layer mapping
- OSI vs TCP/IP comparison
