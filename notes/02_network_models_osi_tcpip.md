# Chapter 2: Network Models — OSI and TCP/IP

## 1. Why do we need a network model?

When computers communicate, many tasks happen together:
- data is generated
- it is formatted
- it is addressed
- it is routed
- it is transmitted
- errors are handled
- the receiver interprets it

If we try to study all of this as one big system, it becomes confusing.
So networking uses a layered model.

### What is a layered model?
A layered model divides communication into smaller parts called layers.
Each layer has a specific responsibility.

### Why layering is useful
- makes design easier
- makes troubleshooting easier
- allows standardization
- helps different vendors' devices work together
- reduces complexity

### GATE point
Questions often ask why layering is needed and what benefit it provides.

## 2. OSI Model

OSI means Open Systems Interconnection.

It is a reference model with 7 layers.

### OSI layer order
1. Application
2. Presentation
3. Session
4. Transport
5. Network
6. Data Link
7. Physical

### Easy memory trick
All People Seem To Need Data Processing

## 3. Layer-by-layer explanation of OSI

### 3.1 Application Layer
This layer is closest to the user.

#### What it does
It provides network services to user applications.

#### Examples
- web browsing
- email
- file transfer
- remote login

#### Common protocols
- HTTP
- HTTPS
- FTP
- SMTP
- DNS

#### Easy meaning
When you open a website, the application layer is involved in supporting that action.

### 3.2 Presentation Layer
This layer prepares data so the application layer can understand it.

#### Main jobs
- translation
- encryption
- compression
- format conversion

#### Example
If one system uses one character set and another system uses another, this layer helps make the data understandable.

#### GATE note
This layer is about data representation, not about sending packets.

### 3.3 Session Layer
This layer manages the conversation between two devices.

#### Main jobs
- start a session
- maintain a session
- end a session
- control dialog
- synchronize communication

#### Example
When you log in to a remote system and keep interacting, the session must stay active.

#### GATE note
Think of this layer as the conversation manager.

### 3.4 Transport Layer
This layer gives end-to-end delivery between processes.

#### Main jobs
- segmentation
- reassembly
- reliability
- flow control
- error control
- port-based communication

#### Protocols
- TCP
- UDP

#### TCP
- reliable
- connection-oriented
- ordered delivery

#### UDP
- fast
- connectionless
- no delivery guarantee

#### GATE note
Transport layer is one of the most important layers in exam questions.

### 3.5 Network Layer
This layer moves packets from source network to destination network.

#### Main jobs
- logical addressing
- routing
- forwarding
- fragmentation

#### Protocols
- IP
- ICMP
- routing protocols

#### GATE note
This layer is where IP address and routing are important.

### 3.6 Data Link Layer
This layer handles delivery on a single link.

#### Main jobs
- framing
- MAC addressing
- error detection
- flow control
- media access

#### Key idea
It takes packets and turns them into frames.

#### GATE note
This layer is associated with frames and MAC addresses.

### 3.7 Physical Layer
This is the lowest layer.

#### Main jobs
- sending bits as signals
- defining electrical/optical/radio characteristics
- bit synchronization
- connector and medium specifications

#### GATE note
Physical layer only cares about bits, not frames or packets.

## 4. Encapsulation in OSI

When data moves from top to bottom, each layer adds control information.

### Simple flow
Data → Segment → Packet → Frame → Bits

### What happens
- transport adds a header
- network adds a header
- data link adds a header and trailer
- physical sends bits through the medium

### Why this is important
Each layer must add information to perform its role.

## 5. Decapsulation in OSI

At the receiver, the reverse process happens.

Bits → Frame → Packet → Segment → Data

Each layer removes the information added by the corresponding sender layer.

## 6. TCP/IP Model

TCP/IP is the model used by the Internet.

It has 4 layers in the common view:
1. Application
2. Transport
3. Internet
4. Network Access

### Why TCP/IP is important
It is not just a theory. It is the actual practical protocol suite used in real networks.

## 7. TCP/IP layers explained

### 7.1 Application Layer
This layer combines OSI’s Application, Presentation, and Session.

#### It provides
- user services
- formatting support
- session handling

#### Examples
- HTTP
- FTP
- SMTP
- DNS
- SSH
- Telnet

### 7.2 Transport Layer
This layer is the same in spirit as OSI transport layer.

#### Protocols
- TCP
- UDP

#### It provides
- end-to-end delivery
- segmentation
- reliability
- multiplexing using ports

### 7.3 Internet Layer
This layer corresponds to OSI network layer.

#### It provides
- logical addressing
- routing
- packet delivery between networks

#### Protocols
- IP
- ICMP
- ARP
- IGMP

### 7.4 Network Access Layer
This layer combines OSI data link and physical layers.

#### It provides
- framing
- physical signaling
- media access
- hardware transmission

## 8. OSI vs TCP/IP

| Feature | OSI | TCP/IP |
|---|---|---|
| Number of layers | 7 | 4 |
| Nature | Reference model | Protocol suite |
| Usage | Study and understanding | Real network communication |
| Developed by | ISO | DoD / DARPA |
| Layer separation | Strict | Less strict |

### Main idea
- OSI helps us understand networking
- TCP/IP helps networks actually work

## 9. Mapping OSI to TCP/IP

| OSI Layer | TCP/IP Layer |
|---|---|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

### Important exam point
The top 3 OSI layers are merged into the TCP/IP application layer.

## 10. Data Units at Each Layer

| Layer | Data Unit |
|---|---|
| Application | Data |
| Presentation | Data |
| Session | Data |
| Transport | Segment |
| Network | Packet |
| Data Link | Frame |
| Physical | Bits |

### Why this matters
This is a common memory-based question in GATE.

## 11. Important Differences

### Routing vs Forwarding
- Routing: deciding the best path
- Forwarding: sending the packet to the next hop

### Frame vs Packet
- Frame: data link unit
- Packet: network unit

### Segment vs Packet
- Segment: transport unit
- Packet: network unit

### Protocol vs Model
- Protocol: set of communication rules
- Model: conceptual layer structure

## 12. Why OSI is still important even though TCP/IP is used

OSI is not the actual Internet protocol suite, but it is extremely useful because:
- it helps in learning
- it helps in exam preparation
- it helps in troubleshooting
- it gives a clear division of responsibilities

## 13. GATE Focus Areas

You should know:
- layer names and sequence
- functions of each layer
- protocols used at each layer
- data unit at each layer
- encapsulation/decapsulation
- OSI vs TCP/IP comparison
- which layer does addressing, routing, framing, encryption, etc.

## 14. PYQ-style questions to practice mentally

- Which layer provides reliable end-to-end delivery?
- Which layer is responsible for routing?
- Which layer deals with MAC addresses?
- Which layers are combined in TCP/IP application layer?
- What is the data unit of the transport layer?
- Which model has 7 layers?
- Which model is used in the Internet?

## 15. Simple Flowchart of Data Flow

Sender Application
   ↓
Presentation
   ↓
Session
   ↓
Transport
   ↓
Network
   ↓
Data Link
   ↓
Physical
   ↓
Communication Medium
   ↓
Physical
   ↓
Data Link
   ↓
Network
   ↓
Transport
   ↓
Session
   ↓
Presentation
   ↓
Receiver Application

## 16. Quick Revision Summary

- OSI has 7 layers.
- TCP/IP has 4 layers.
- OSI is conceptual.
- TCP/IP is practical.
- Transport handles end-to-end delivery.
- Network handles routing and IP.
- Data link handles frames and MAC.
- Physical handles bits and signals.
- Top 3 OSI layers map to TCP/IP application layer.

## 17. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- IEEE Communications Society: https://www.comsoc.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach