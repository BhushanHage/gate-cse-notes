# Chapter 5: Network Layer

## 1. What is the Network Layer?

The Network Layer is the third layer of the OSI model. Its main responsibility is to move packets from the source host to the destination host, even if the two hosts are in different networks.

### Main idea
The data link layer works inside one link, but the network layer works across multiple networks.

### In simple words
This layer decides how data should travel from one machine to another across the internet or a large internetwork.

### GATE point
The network layer works with packets and IP addresses.

---

## 2. Why do we need the Network Layer?

When a device wants to send data to another device that is not directly connected, it needs a way to:
- identify the destination logically
- find a route
- forward data through intermediate routers

The network layer provides this functionality.

### Why it is important
Without the network layer, communication would be limited only to directly connected devices.

---

## 3. Main Responsibilities of the Network Layer

The network layer is responsible for:

1. Logical addressing
2. Routing
3. Forwarding
4. Fragmentation and reassembly
5. Congestion handling in some cases
6. Internetworking

---

## 4. Logical Addressing

### What is logical addressing?
Logical addressing is the use of an address that identifies a device in a network and helps in routing.

### Example
The most common logical address is the IP address.

### IP addresses
- IPv4: 32-bit address
- IPv6: 128-bit address

### Difference from MAC address
- MAC address is physical and used locally
- IP address is logical and used globally for routing

### GATE point
Network layer uses IP addresses, not MAC addresses.

---

## 5. Routing

### What is routing?
Routing is the process of selecting the best path for a packet to travel from source to destination.

### Why routing is needed
In large networks, there may be many possible paths between two hosts. Routing chooses one of them.

### Who performs routing?
Routers perform routing.

### Routing table
A router maintains a routing table containing information such as:
- destination network
- next hop
- cost/metric
- interface

### GATE point
Routing is a network-layer function.

---

## 6. Forwarding

### What is forwarding?
Forwarding is the actual act of sending a packet from one router interface to the next hop.

### Difference from routing
- Routing: chooses the path
- Forwarding: sends along the chosen path

### GATE point
Do not confuse routing with forwarding.

---

## 7. Fragmentation and Reassembly

### Why fragmentation is needed
Different networks may support different maximum frame sizes. A packet may be too large to travel over a link.

### Fragmentation
The network layer can divide a large packet into smaller pieces called fragments.

### Reassembly
At the destination, the fragments are reassembled into the original packet.

### Important note
In IPv4, fragmentation can occur at routers. In IPv6, fragmentation is handled differently.

### GATE point
Fragmentation is an important concept in network layer questions.

---

## 8. Internetworking

### What is internetworking?
Internetworking is the connection of multiple networks so they can communicate as one larger system.

### Example
The internet is an internetwork made of many smaller networks connected together.

### Role of the network layer
It allows communication across different networks and different transmission technologies.

---

## 9. Connectionless and Connection-Oriented Service

### Connectionless service
Each packet is treated independently.

#### Example
IP is connectionless.

#### Features
- no prior setup
- packets may take different paths
- simple and scalable

### Connection-oriented service
A logical connection is established before data transfer.

#### Example
Some network services or virtual circuit approaches

#### Features
- setup required
- more control
- more overhead

### GATE point
The Internet network layer is mainly connectionless.

---

## 10. Network Layer Protocols

### 10.1 Internet Protocol (IP)
IP is the most important network layer protocol.

#### Functions
- logical addressing
- packet delivery
- routing support

#### Versions
- IPv4
- IPv6

---

### 10.2 Internet Control Message Protocol (ICMP)
ICMP is used for error reporting and control messages.

#### Example uses
- ping
- destination unreachable
- time exceeded

### GATE point
ICMP is used for diagnostics, not for normal data transfer.

---

### 10.3 Address Resolution Protocol (ARP)
ARP maps an IP address to a MAC address in a local network.

#### Why it is needed
A host may know the IP address of another host but still need the MAC address to send the frame locally.

### GATE point
ARP works between network layer and data link layer.

---

### 10.4 Routing protocols
Routing protocols help routers exchange routing information.

#### Examples
- RIP
- OSPF
- BGP

---

## 11. IPv4 Addressing

### IPv4
IPv4 uses 32-bit addresses.

#### Example
192.168.1.10

### Structure
An IPv4 address is written in dotted decimal notation.

### Subnetting idea
An IP address has:
- network part
- host part

### Why subnetting matters
It helps divide a large network into smaller manageable networks.

---

## 12. IPv6 Addressing

IPv6 was introduced because IPv4 address space is limited.

### IPv6 features
- 128-bit addresses
- much larger address space
- simpler header structure
- better support for modern networking

### Example
2001:db8::1

### GATE point
IPv6 uses a much larger address space than IPv4.

---

## 13. Datagram / Packet Structure

The network layer data unit is called a packet or datagram.

### Main fields in an IP packet
- source address
- destination address
- TTL / hop limit
- protocol
- header checksum in IPv4
- fragmentation information in IPv4

### Why header is needed
The header contains control and routing information.

---

## 14. TTL (Time To Live)

### What is TTL?
TTL prevents packets from circulating forever in the network.

### Working
Each router decreases TTL by 1. If TTL becomes zero, the packet is discarded.

### GATE point
TTL avoids infinite loops.

---

## 15. Subnetting and CIDR

### Subnetting
Subnetting divides one large network into smaller sub-networks.

### CIDR
CIDR stands for Classless Inter-Domain Routing.

#### Example
192.168.1.0/24

### Why CIDR is used
- efficient address allocation
- flexible routing
- route aggregation

### GATE point
CIDR is commonly tested with IP addressing questions.

---

## 16. Distance Vector and Link State Routing

### 16.1 Distance Vector Routing
Each router shares its routing table with neighbors.

#### Example protocol
RIP

#### Limitation
Can suffer from slow convergence and routing loops.

---

### 16.2 Link State Routing
Each router builds a complete map of the network and computes shortest paths.

#### Example protocol
OSPF

#### Advantage
Faster convergence and better scalability than distance vector routing.

### GATE point
Know the difference between distance vector and link state routing.

---

## 17. Routing Algorithms

### Shortest path routing
Choose the path with minimum cost or distance.

### Flooding
A packet is sent on all possible outgoing links except the incoming one.

#### Advantage
Reliable delivery in some special cases

#### Disadvantage
Creates a lot of traffic

### GATE point
Routing algorithms are a frequent theory topic.

---

## 18. Congestion in the Network Layer

### What is congestion?
Congestion occurs when too many packets arrive at a network node or link and the system cannot handle them efficiently.

### Effects
- long delay
- packet loss
- queue buildup
- reduced throughput

### Congestion control
Mechanisms used to reduce congestion include:
- traffic shaping
- queue management
- admission control

### GATE point
Congestion control is related to network performance.

---

## 19. Network Layer Devices

### Router
A router operates at the network layer.

#### It uses
- IP addresses
- routing tables

#### It does
- packet forwarding
- path selection between networks

### GATE point
Router = network layer device.

---

## 20. Comparison Tables

### Network layer vs data link layer
| Feature | Network Layer | Data Link Layer |
|---|---|---|
| Delivery | Source to destination | Node to node |
| Address used | IP address | MAC address |
| Data unit | Packet | Frame |
| Main job | Routing | Framing, MAC, error detection |

### IPv4 vs IPv6
| Feature | IPv4 | IPv6 |
|---|---|---|
| Address length | 32 bits | 128 bits |
| Address space | Limited | Very large |
| Format | Decimal dotted notation | Hexadecimal notation |
| Need for NAT | Common | Less required |

### Distance vector vs link state
| Feature | Distance Vector | Link State |
|---|---|---|
| Information shared | Routing table | Topology information |
| Convergence | Slower | Faster |
| Example | RIP | OSPF |

---

## 21. Important GATE Questions from This Chapter

You should be able to answer:
- What is logical addressing?
- What is routing?
- What is forwarding?
- Why is fragmentation needed?
- What does ARP do?
- What is the role of ICMP?
- What is TTL?
- What is subnetting?
- What is the difference between IPv4 and IPv6?
- What is the difference between distance vector and link state routing?

---

## 22. PYQ Focus Areas

These topics are especially important:
- IP addressing
- subnetting
- CIDR
- routing tables
- TTL
- ARP
- ICMP
- routing algorithms
- distance vector vs link state
- IPv4 vs IPv6

---

## 23. Quick Revision Summary

- The network layer provides source-to-destination delivery.
- It works with packets and IP addresses.
- Routing chooses the path.
- Forwarding sends the packet to the next hop.
- ARP maps IP to MAC.
- ICMP is used for error reporting and diagnostics.
- TTL prevents looping.
- Routers work at the network layer.

---

## 24. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach

---

## 25. Final GATE Tip

For the network layer, focus on:
- IP addressing
- routing and forwarding
- fragmentation
- subnetting
- routing protocols
- router behavior
- IPv4 vs IPv6